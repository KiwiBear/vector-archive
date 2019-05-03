# The Vector Archive
This repo is intended to house archives for the Anki Vector (née Victor) robot.

# Useful addresses hardcoded in to the Vector app & OS
* Device certs: https://session-certs.token.global.anki-services.com/vic/{serial_number}
* Accounts API: https://accounts.api.anki.com/1/sessions
* Locations API: https://locations.api.anki.com/1/locations
* OTA Updates delivered from: http://ota.global.anki-services.com/vic/prod/full/latest.ota

# Vector SDK Registration Flow
* Cert downloaded for Vector downloaded from https://session-certs.token.global.anki-services.com/vic/{serial_number}
* User session established with Anki using the Accounts API
* Session token Base64 encoded
* Machine hostname Base64 encoded
* Encoded session token & machine hostname sent to Vector API (/v1/user_authentication)
* Vector responds with Base64 encoded OAuth token (client_token_guid)
* guid decoded and stored in the sdk_config.ini

# Vector API Usage
* Nearly all calls to Vector are POSTS
* /v1/user_authentication is the only request that doesn't require a bearer token

# Currently known Vector API Endpoints
|	Method	|	API Endpoint URI	|	Method	|	API Endpoint URI	|
|	---	|	---	|	---	|	---	|
|	POST	|	 "/v1/alexa_auth_state"	|	POST	|	 "/v1/feature_flag_list"	|
|	POST	|	 "/v1/alexa_opt_in"	|	POST	|	 "/v1/find_faces"	|
|	POST	|	 "/v1/app_intent"	|	POST	|	 "/v1/flash_cube_lights"	|
|	POST	|	 "/v1/assume_behavior_control"	|	POST	|	 "/v1/forget_preferred_cube"	|
|	POST	|	 "/v1/audio_feed"	|	POST	|	 "/v1/get_latest_attention_transfer"	|
|	POST	|	 "/v1/battery_state"	|	POST	|	 "/v1/get_onboarding_state"	|
|	POST	|	 "/v1/camera_feed"	|	POST	|	 "/v1/go_to_pose"	|
|	POST	|	 "/v1/cancel_action_by_id_tag"	|	POST	|	 "/v1/is_image_streaming_enabled"	|
|	POST	|	 "/v1/cancel_face_enrollment"	|	POST	|	 "/v1/list_animation_triggers"	|
|	POST	|	 "/v1/capture_single_image"	|	POST	|	 "/v1/list_animations"	|
|	POST	|	 "/v1/check_cloud_connection"	|	POST	|	 "/v1/look_around_in_place"	|
|	POST	|	 "/v1/check_update_status"	|	POST	|	 "/v1/nav_map_feed"	|
|	POST	|	 "/v1/connect_cube"	|	POST	|	 "/v1/photo"	|
|	POST	|	 "/v1/create_fixed_custom_object"	|	POST	|	 "/v1/photos_info"	|
|	POST	|	 "/v1/cubes_available"	|	POST	|	 "/v1/protocol_version"	|
|	POST	|	 "/v1/define_custom_object"	|	POST	|	 "/v1/pull_jdocs"	|
|	POST	|	 "/v1/delete_custom_objects"	|	POST	|	 "/v1/request_enrolled_names"	|
|	POST	|	 "/v1/delete_photo"	|	POST	|	 "/v1/roll_block"	|
|	POST	|	 "/v1/disconnect_cube"	|	POST	|	 "/v1/say_text"	|
|	POST	|	 "/v1/display_face_image_rgb"	|	POST	|	 "/v1/sdk_initialization"	|
|	POST	|	 "/v1/dock_with_cube"	|	POST	|	 "/v1/send_onboarding_input"	|
|	POST	|	 "/v1/drive_off_charger"	|	POST	|	 "/v1/set_eye_color"	|
|	POST	|	 "/v1/drive_on_charger"	|	POST	|	 "/v1/set_face_to_enroll"	|
|	POST	|	 "/v1/enable_face_detection"	|	POST	|	 "/v1/set_preferred_cube"	|
|	POST	|	 "/v1/enable_image_streaming"	|	POST	|	 "/v1/start_update_engine"	|
|	POST	|	 "/v1/enable_marker_detection"	|	POST	|	 "/v1/thumbnail"	|
|	POST	|	 "/v1/enable_mirror_mode"	|	POST	|	 "/v1/update_account_settings"	|
|	POST	|	 "/v1/enable_motion_detection"	|	POST	|	 "/v1/update_and_restart"	|
|	POST	|	 "/v1/erase_all_enrolled_faces"	|	POST	|	 "/v1/update_enrolled_face_by_id"	|
|	POST	|	 "/v1/erase_enrolled_face_by_id"	|	POST	|	 "/v1/update_settings"	|
|	POST	|	 "/v1/event_stream"	|	POST	|	 "/v1/user_authentication"	|
|	GET	|	 "/v1/event_stream"	|	POST	|	 "/v1/version_state"	|
|	POST	|	 "/v1/feature_flag"	|		|		|

# DNS Entries used by Vector #
| DNS Name | Record Type | Value | Usage |
| --- | --- | --- | --- |
| jdocs.api.anki.com | CNAME | sai-jdocs-production-a118882cab770eaf.elb.us-west-2.amazonaws.com | Cloud storage for Vector data |
| chipper.api.anki.com | CNAME | sai-chipper-voice-production-c3986a3cf3880c40.elb.us-west-2.amazonaws.com | Voice NLP service |
| locations.api.anki.com | CNAME | sai-locations-production-867039238.us-west-2.elb.amazonaws.com | |
| accounts.api.anki.com | CNAME | sai-go-accounts-production-639190070.us-west-2.elb.amazonaws.com | User identity service |
| token.api.anki.com | CNAME | sai-token-service-production-4e4f609b8a1ff82b.elb.us-west-2.amazonaws.com | |
| | | | |
| conncheck.global.anki-services.com | A | 52.84.64.17 | |
| conncheck.global.anki-services.com | A | 52.84.64.34 | |
| conncheck.global.anki-services.com | A | 52.84.64.84 | |
| conncheck.global.anki-services.com | A | 52.84.64.187 | |
| ota.global.anki-services.com | A | 52.84.64.125 | OTA firmware distribution | 
| ota.global.anki-services.com | A | 52.84.64.169 | OTA firmware distribution | 
| ota.global.anki-services.com | A | 52.84.64.185 | OTA firmware distribution | 
| ota.global.anki-services.com | A | 52.84.64.186 | OTA firmware distribution | 
| | | | |
| forums.anki.com | CNAME | anki.bydiscourse.com | Developer/User Forums |

# Vector Cert and Auth Files #
Since we don't know how long the servers that create your SDK_Config information will stay up, it is very important to configure your Vector SDK and back up these files.

By default they can be find in your C:\Users\[username]\.anki_vector folder.

You will find a .cert file for each Vector. It will be named Vector-[####]-[xxxxxxxx].cert where #### is the Vector name, and xxxxxxxx is the serial number.

The other file will be the sdk_config.ini file, which will contain information for each Vector you configure.

Within the file you will find your serial number, file location for the cert, ip address assigned to that Vector, Vector name, and guid value.

Back this folder up in multiple locations. If you lose this guid and the auth servers go down, you're going to have a bad time.
