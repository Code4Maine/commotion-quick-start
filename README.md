commotion-quick-start
=====================

A quick start interface for commotion OpenWRT routers.

This package will work as such.


1) A main_view quick-start(qs) page is called running any functions assigned to it.
1a) The main qs page calls a header section, passing it any value(s)
1b) The main qs page calls a main section, passing it any value(s)
1c) The main qs page calls a set of buttons [button(text, image, action)]
1d) The main qs page is viewed

2) A Button is clicked
2a) That button makes a call to a function in the controller designated by the buttons action.
2b) That function runs, and completes by displaying another main_view which starts the process over again.

This will allow for any modification of any UX path to be done in the controller without messing around with the views. All modeling will be done withing the "sections." As such, if a CBI model is called it will be embedded within the main section of some main_view. This will allow for buttons to make UCI calls as well as load templates.

*view

** main
QS_welcome_main
QS_basicInfo_main
QS_nearbyMesh_main
QS_UCI_main "the main section of this page calls whatever cbi map it is passed"
QS_chosenMeshDefault_main
QS_errorPage_main
QS_connectedNodes_main
QS_wait4Reset_main
QS_sharingPrefs_main
QS_uploadConfig_main
QS_chooseConfig_main
QS_newNetwork_main

** module

QS_bigButton "A single big button that takes its text from whatever it is passed"
QS_infoBanner "A banner that takes and displays a main header and a explanation"
QS_logoInfoBanner "same as info banner, but with a logo above it"
QS_buttons "a view that displays any number (within reason) of buttons that it is passed and assigns them corresponding actions"
QS_meshDisplay "a view that takes a list of nearby mesh networks and displays them, with "known" network types highlighted. also includes a key to highlighting"
QS_upload "a view that uploads a file to a specific location based upon the values it is passed"
QS_meshInfo "a view that displays a customized list of charicteristics of a network that a user is attempting to join."
QS_errorMessage "a view that displays a customized error message based upon the error value passed to it (matched to a error_dictionary model)
QS_nodeNeighbors "a section that displays a counter of visible nodes with flavor text depending upon the ammount of nodes"
QS_recconectTime "a section that displays a countdown timer and the current node AP to prompt a user to recconect after the node has finished restarting"
QS_sharing "a section that shows a simple checklist of sharing settings that a user can use to customize their sharing settings."

* controller
QS_main
QS_UCI
QS_buttons

* model "the various models within this section need to be user & developer tested to determine the flavor/explanitory text that goes along-side them, the best possible groupings of configurations, and 

* resources

** buttons
inner_equal
inner_x
inner_arrow
inner_check
inner_bullseye
inner_dot
inner_diamond
inner_plus
outer_circle