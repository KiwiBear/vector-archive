# The Vector Archive
This repo is intended to house archives for the Anki Vector (née Victor) robot.

# Useful addresses hardcoded in to the Vector app & OS
* Accounts API: https://accounts.api.anki.com/1/sessions
* Locations API: https://locations.api.anki.com/1/locations
* OTA Updates delivered from: http://ota.global.anki-services.com/vic/prod/full/latest.ota

# Vector SDK Registration Flow
* Self-signed cert downloaded from Vector
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
