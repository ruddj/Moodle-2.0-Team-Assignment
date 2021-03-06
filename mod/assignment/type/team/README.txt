Steps to install team assignments type to a 2.0.x Moodle installation
====================================================================

1) unzip team-assignment-type.zip at the moodle root or manually copy the team directory
   to <moodle root>/mod/assignment/type/

3) insert the extra lines contained in moodle-file.patch into <moodle root>/file.php. 
   Delete moodle-file.patch after inserting the extra lines.

4) log in to your moodle site as Admin user.

5) visit the Admin notifications page.

6) run admin notifications. Two tables (team and team_student) will be installed.


Turnitin integration
====================
Some Moodle sites may be using the Turnitin integration developed by Catalyst IT Ltd. 
See (http://moodle.org/mod/data/view.php?d=13&rid=1562). If so, then it is likely that they
will want to use Turnitin with the Team assignment type. Optional, Turnitin code 
has been added to the Team assignment type in the following functions:

* function print_team_answer($teamid)
* function print_user_files($userid=0, $return=false, $teamid)
* function upload_file()
* function finalize()

1. If you wish to enable Turnitin integration then the code in the above functions must be uncommented.
2. Replace the code contained in assignment-lib.patch into <moodle root>/mod/assignment/lib.php.
3. Apply the lib-turnitinlib.patch for <moodle root>/lib/turnitinlib.php
** Note that the team assignment Turnitin integration will only work if your Moodle installation has
   a valid Turnitin license and the Catalyst IT Ltd Turnitin integration module has been installed
