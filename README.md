# Recentworks
This is a python code that lists all volumes in an Aws account
Iterate through these volumes
See If they have EnterpriseAppID tag,for each volume
Also see if the EnterpriseAppID is compliant or not,that based on the standard of naming,for the organization
if EnterpriseAppID doesnt exist for a volume, it finds the attached EC2 instance and see if that instance has EnterpriseAppID tag and copies that
If the the Instance attached doesnt have EnterpriseAppID tag, the volume is tagged "EC2-EnterpriseAppID-missing"
Back to logic 6, if the EnterpriseAppID exists, then, see if it has some non- alphanumeric strings attached to it, if yes, trim it out.
Then for volumes with unattached instances, create  tags, "AttachedTo" as key and value as "N/A" and also "EnterpriseAppID" as key while value is "Not found"
For all volumes, create a new tag "Attached To" and skip if volume already have the Tag, the value of this Tag is the EC2 instance attached to
Update all "AttachedTo" tag according to the new instance they have been attached to if that happens to help in cost analysis as well
