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
|	post	|	/v1/assume_behavior_control	|	post	|	/v1/event_stream	|
|	post	|	/v1/audio_feed	|	get	|	/v1/event_stream	|
|	post	|	/v1/battery_state	|	post	|	/v1/find_faces	|
|	post	|	/v1/camera_feed	|	post	|	/v1/flash_cube_lights	|
|	post	|	/v1/cancel_action_by_id_tag	|	post	|	/v1/forget_preferred_cube	|
|	post	|	/v1/cancel_face_enrollment	|	post	|	/v1/go_to_pose	|
|	post	|	/v1/capture_single_image	|	post	|	/v1/is_image_streaming_enabled	|
|	post	|	/v1/connect_cube	|	post	|	/v1/list_animation_triggers	|
|	post	|	/v1/create_fixed_custom_object	|	post	|	/v1/list_animations	|
|	post	|	/v1/cubes_available	|	post	|	/v1/look_around_in_place	|
|	post	|	/v1/define_custom_object	|	post	|	/v1/nav_map_feed	|
|	post	|	/v1/delete_custom_objects	|	post	|	/v1/photo	|
|	post	|	/v1/delete_photo	|	post	|	/v1/photos_info	|
|	post	|	/v1/disconnect_cube	|	post	|	/v1/protocol_version	|
|	post	|	/v1/display_face_image_rgb	|	post	|	/v1/request_enrolled_names	|
|	post	|	/v1/dock_with_cube	|	post	|	/v1/roll_block	|
|	post	|	/v1/drive_off_charger	|	post	|	/v1/say_text	|
|	post	|	/v1/drive_on_charger	|	post	|	/v1/sdk_initialization	|
|	post	|	/v1/enable_face_detection	|	post	|	/v1/set_eye_color	|
|	post	|	/v1/enable_image_streaming	|	post	|	/v1/set_face_to_enroll	|
|	post	|	/v1/enable_marker_detection	|	post	|	/v1/set_preferred_cube	|
|	post	|	/v1/enable_mirror_mode	|	post	|	/v1/thumbnail	|
|	post	|	/v1/enable_motion_detection	|	post	|	/v1/update_enrolled_face_by_id	|
|	post	|	/v1/erase_all_enrolled_faces	|	post	|	/v1/user_authentication	|
|	post	|	/v1/erase_enrolled_face_by_id	|	post	|	/v1/version_state	|
