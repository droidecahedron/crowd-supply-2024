
<p align="center">
  <img src="https://github.com/droidecahedron/crowd-supply-2024/assets/63935881/87097c00-54b2-45a6-8a33-311280c2a21f">
</p>

# Required Materials
## Hardware
- Thingy:91 <img src="https://github.com/droidecahedron/crowd-supply-2024/assets/63935881/2f0c115a-7909-4bda-8d90-6a85aa579ebf" width=4% height=4%> <img src="https://github.com/droidecahedron/crowd-supply-2024/assets/63935881/b1be92a2-11c2-48ad-bf37-a4dfbbcf07ac" width=4% height=4%>

- Micro-USB cable (likely to USBA)
  <img src="https://github.com/droidecahedron/crowd-supply-2024/assets/63935881/c5b5e36f-6911-4b33-af32-0ccff6381a3d" width=4% height=4%>

- Laptop 💻 setup with software ahead of time
## Software
### Video Guide
[![SDK Installation Instructions](https://img.youtube.com/vi/EAJdOqsL9m8/0.jpg)](https://www.youtube.com/watch?v=EAJdOqsL9m8)

☝️ Goes through the following checklist 👇

**These are large downloads and take a long time. Please complete before the workshop.**
- nRF Connect SDK
    - nRF CLI Tools (🔗 [Link](https://www.nordicsemi.com/Products/Development-tools/nRF-Command-Line-Tools/Download?lang=en#infotabs))
    - nRF Connect for Desktop ([Link](https://www.nordicsemi.com/Products/Development-tools/nRF-Connect-for-Desktop/Download#infotabs))
    - nRF Connect for VS Code ([Link](https://marketplace.visualstudio.com/items?itemName=nordic-semiconductor.nrf-connect))
        - Click on extension icon in sidebar:
	        - ⏳ Click **Install Toolchain** ⏳
		        - Select v.2.6.1
	        - ⏳ Click **Manage SDKs** --> **Install SDK** ⏳
		        - Select v.2.6.1
		        - Use default directory
     - nRF Connect for VS Code Extension Pack  ([Link](https://marketplace.visualstudio.com/items?itemName=nordic-semiconductor.nrf-connect-extension-pack))
- nRF Connect for Desktop ([Link](https://www.nordicsemi.com/Products/Development-tools/nRF-Connect-for-Desktop/Download#infotabs))
      - Install Programmer app
      - Install Serial Terminal app


# Workshop Outline
  - Intro Slides / chalk talk
    - Intro to Thingy:91 ([Link](https://www.nordicsemi.com/Products/Development-hardware/Nordic-Thingy-91))
    - Intro to nRF Connect for Desktop
    - Intro to VS Code and Nordic VSC Extensions
    - Intro to nRF Cloud
    - Intro to the nRF Cloud multi-service sample: ([Link](https://docs.nordicsemi.com/bundle/ncs-2.6.1/page/nrf/samples/cellular/nrf_cloud_multi_service/README.html))
  - Hands on

# Initial Setup
- clone the workshop git repo: https://github.com/droidecahedron/crowd-supply-2024.git

# Walkthrough
## Add the application to VSCode:

- Click on the nRF Connect icon in the left hand ribbon
- Click on Open an existing application
- Navigate to the base folder inside the repo
- Click Open:<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/be469b34-96e5-41d3-93b1-8b76191241c5" width="500"/>

## Under Applications at the bottom of the left pane 
- Click on Add build configuration 
- Select the “thingy91_nrf9160_ns” board
- Click Build Configuration<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/383b05dc-9d52-4514-ac83-f7b59f3881c2" width="500"/>

## Launch nRF Connect for Desktop 
- Click on the Programmer app <br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8958ac27-c970-4f15-b830-521fb954d9d6" width="500"/>

## On your Thingy:91: 
- Power off your Thingy:91 and remove the orange cover.
- Hold down the center button 
- Turn it on then release the center button --> it is now in MCUboot mode (USB/serial bootloader) 
- Connect it to your notebook with a micro USB cable

## In the Programmer app: 
- Click on Add file 
- Navigate to crowd-supply-2024/base/build/zephyr 
- Select app_signed.hex 
- Click on Select Device 
- Select Nordic Thingy:91<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/b2cda5af-d629-402f-b344-554e043c54b2" width="500"/>
- Click Write
- Click Write again
- The app will now program the device.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/ef736442-0a70-4cfa-9102-e99f01aa2c65" width="500"/><br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8e2644fd-9310-40f7-9ee3-723f3df4448c" width="500"/><br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8440f326-0cc4-427f-9be9-aa899a97bf24" width="500"/>

## Create your nRF Cloud account:
- Open a browser to: https://nrfcloud.com([Link](https://nrfcloud.com))
- Click Register<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/9124ac0a-7dce-4a3d-b00d-d34264cd05ee" width="500"/>
- Fill out the form.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/c644e7b0-2ecf-4379-844e-231d008ee844" width="500"/>
- Click Create Account.
- Receive confirmation code vial email.
- Confirm the code.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8b023421-6171-4cbb-ba5d-f0ece6449769" width="500"/>

## Register your SIM card:
- Click on Device Management --> SIM Cards
- Click Add SIM.
- Fill out the form.
- Click Activate SIM.
- Follow any additional instructions.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/04caff91-8451-475c-81b9-7d8f8694e5cb" width="500"/>

## View serial output:
-  While your device is running, it generates log messages, which you can view using Serial Terminal.
- Open Serial Terminal from nRF Connect for Desktop.
- Click Select Device and select Thingy:91.
- Remove the SIM from the carrier and insert into the SIM slot on your Thingy:91.
- Cycle power on the Thingy using the toggle switch. 
- The Serial Terminal application should automatically reconnect.
- View the log messages:
	- The device will wait for network connectivity and then attempt to connect to nRF Cloud.
	- The initial connection attempt will fail, this is normal. The cloud is provisioning the device.
	- Wait ~15 seconds before proceeding.

## Add your Thingy:91 to your account:
- Click on Device Management --> Devices.
- Click Add Devices.
- Click LTE Device.
- Fill out the form with info from the white sticker.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/bd1f27ff-1673-4750-b9fa-52c1b1aaffd8" width="500"/><br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/6028e6c9-3bf4-43db-85ca-8ba9b520f35d" width="500"/>
- Your device should now be connected to your nRF Cloud account.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/a7d967c0-a04b-499a-805c-b3091363a0b0" width="500"/>
- Take a tour of this page.

# Customizing The Sample For Solving Puzzles

## Add a button handler in application.c
- In VSCode, in the Explorer, view the source for `prj.conf`. 
- Add: `CONFIG_DK_LIBRARY=y` 
- View the source for `application.c`. 
- Add: `#include <dk_buttons_and_leds.h>` 
- Add a call in `main_application_thread_fn()` to `dk_buttons_init(button_handler);`
```C
void main_application_thread_fn(void)
{
	dk_buttons_init(button_handler);
```
- Add a new function: 
```C
static void button_handler(uint32_t button_state, uint32_t has_changed) 
{ 
	if (has_changed & DK_BTN1_MSK) { 
		if ((button_state & DK_BTN1_MSK) == DK_BTN1_MSK) { 
			LOG_INF("Button pressed!"); 
		} else { 
			LOG_INF("Button released!"); 
		} 
	} 
}
```
- Build your changes. 
- Disconnect ⏏️ the device in Serial Terminal.
- Power off your Thingy:91.
- In the Programmer app, hit Reload files. 
- Place your Thingy:91 back in MCUboot mode, reconnect to it in the Programmer app, then click Write.
- When complete, reconnect the device in Serial Terminal and watch the log output. 
- Look for log messages when you press the button.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/30c1c0db-ad21-4b6c-b424-2d54ac4854a5" width="500"/>

## Add variables and functions to maintain the most recent and best location data 
- Add two global variables: 
```C
static struct location_data last_location; 
static int64_t last_location_ts; 
```
- Add a `clear_location()` function:
```C
static void clear_location(void) 
{ 
	last_location_ts = 0; 
	memset(&last_location, 0, sizeof(last_location)); 
	LOG_INF("Location cleared."); 
} 
```
- Add a `store_location()` function.
- Here's what it does:
  - Within a 10 minute window, record the location data which has the best accuracy.
  - Outside of that window, overwrite with the current location measurement regardless of accuracy.
```C
static void store_location(const struct location_data *loc) 
{ 
	int64_t new_ts; 
	int err = date_time_now(&new_ts); 

	if (err) { 
		LOG_ERR("Failed to obtain current time, error %d", err); 
		return; 
	} 

	if (last_location_ts && 
	 ((new_ts - last_location_ts) < (10 * 60 * 1000))) { /* 10 minutes */ 
		/* Probably have not physically moved much, so require better accuracy */ 
		if (loc->accuracy > last_location.accuracy) { 
			LOG_INF("Ignoring less accurate location"); 
			return; 
		} 
		LOG_INF("More accurate location found; storing"); 
	} else { 
		LOG_INF("Location stale; storing"); 
	} 
	last_location = *loc; 
	last_location_ts = new_ts; 
} 
```
- Add a `send_location()` function.
  - Send it as an nRF Cloud `ALERT` in string format, including the latitude, longitude, accuracy, and timestamp. 
```C
static void send_location(void) 
{ 
	char msg[100]; 

	if (!last_location_ts) { 
		LOG_ERR("No data to send yet!"); 
		short_led_pattern(LED_FAILURE); 
		return; 
	} 
	snprintk(msg, sizeof(msg), "MARK,%.06f,N,%.06f,W,radius,%.01f,ts,%lld", 
		last_location.latitude, 
		last_location.longitude, 
		(double)last_location.accuracy, 
		last_location_ts); 
	(void)nrf_cloud_alert_send(ALERT_TYPE_MSG, 0, msg); 
	LOG_INF("Sent %s", msg); 
	short_led_pattern(LED_SUCCESS); 
} 
```
- Call the `store_location()` function from the existing `on_location_update()` function. 
```C
static void on_location_update(const struct location_event_data * const location_data) 
... 
	store_location(&location_data->location);  /* <- new line */
} 
#endif  /* CONFIG_LOCATION_TRACKING */ 
``` 
- Call `send_location()` when the button is pressed, and `clear_location()` when released. 
```C
static void button_handler(uint32_t button_state, uint32_t has_changed) 
{ 
	if (has_changed & DK_BTN1_MSK) { 
		if ((button_state & DK_BTN1_MSK) == DK_BTN1_MSK) { 
			LOG_INF("Button pressed!"); 
			send_location();  /* <- new line */
		} else { 
			LOG_INF("Button released!"); 
			clear_location();  /* <- new line */
		} 
	} 
} 
``` 
- Try it out!
- If you press the button before you have a new location, the Thingy:91 blinks red, and you see an error in the log:<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/42d583c7-ef03-46fa-b1de-b341fa60656d" width="500"/>
- Once you have a location, pressing the button sends an alert to your account, and you see that in the log:<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/814f7b87-03fe-4b39-9434-4cc8ac5f276f" width="500"/>
- **NOTE: this is a log captured over Bluetooth LE using the nRF Toolbox app UART Util Service.**
- Enable BLE logging by editing the config file `Config.txt` on the mass storage device that appears when you connect over USB.
 
```
==========================================
  Nordic Thingy:91 Configuration options
==========================================
The parameters below can be changed at runtime.

NOTE: For changes to take effect,
safely disconnect (unmount) the drive and disconnect the USB cable.
==========================================
BLE_ENABLED=1
BLE_NAME=Thingy:91 UART
```
- You will also see it appear as an alert in your nRF Cloud account on the device page:<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/7895e0f0-578a-4d61-9696-b197e92c012e" width="500"/>

## Receiving messages from the cloud
- In `cloud_connection.c`, add one line to `cloud_event_handler()` in the `NRF_CLOUD_EVT_RX_DATA_GENERAL` case: 
```C 
case NRF_CLOUD_EVT_RX_DATA_GENERAL: 
		LOG_DBG("NRF_CLOUD_EVT_RX_DATA_GENERAL"); 
		LOG_DBG("%d bytes received from cloud", nrf_cloud_evt->data.len); 

		LOG_WRN("Message: %*s", nrf_cloud_evt->data.len, (char *)nrf_cloud_evt->data.ptr); /* <- new line */ 
```
- From your nRF Cloud account, send a message to the device in the Terminal card in JSON format like this: 
```JSON
{"appId":"Hello from Teardown 2024!"} 
```
- This will appear in the logs on the device:<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/569cdc3f-70fc-4985-8d24-311a2f965d49"/>

## Power draw improvements
- Optimize some Kconfig settings in `prj.conf`: 
```
CONFIG_TEMP_ALERT_LIMIT=50 
CONFIG_SENSOR_SAMPLE_INTERVAL_SECONDS=240 
CONFIG_LOCATION_TRACKING_SAMPLE_INTERVAL_SECONDS=120  
```
- Bonus: keep LED off longer by modifying the `led_pattern_idle()` function in `led_control.c`: 
```C
static void led_pattern_idle(int frame_number) 
{ 
	if (IS_ENABLED(CONFIG_LED_INDICATOR_RGB)) { 
		/* A triangle wave between 0 and 10 with a pause between */ 
		int breath = MAX((abs((frame_number % 40) - 20) - 10), 0); 
		/* Breathe back and forth between cyan and black */ 
		led_set_rgb(0, breath, breath); 
	} else if (IS_ENABLED(CONFIG_LED_INDICATOR_4LED)) { 
```
# Puzzle Hunt
- If you plan to participate in the Puzzle Hunt, send Josh at Crowd Supply your device id and your API_KEY 
- Your device id is shown in your nRF Cloud account in the devices view.<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/7e324b73-c018-49b5-beb4-3f201698b339" width="500"/>
- Your API_KEY is visible on your account page:<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/00c8a941-f44a-44d2-a6a7-b68137035ff7" width="500"/>
- When Teardown 2024 and the Puzzle Hunt are complete, don't forget to return to your account page and click **Regenerate API Key**.
- You might want to update the modem firmware in your Thingy:91 to the latest version.
  - This will improve the speed and accuracy of GPS fixes.
  - Your Thingy:91 comes with mfw_nrf9160_1.3.4 installed.
  - There is a FOTA update feature (firmware over the air) in nRF Cloud that would let you incrementally update the modem firmware from mfw_nrf9160_1.3.4 to mfw_nrf9160_1.3.5, and then again from mfw_nrf9160_1.3.5 to mfw_nrf9160_1.3.6.
  - **Note**: doing these FOTA updates will consume about 1/3 of the free data allowance on your SIM. This should be OK for the weekend.
<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/10f01976-697e-48a3-8ac8-1d88a3bbe8ee" width="500"/>
<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/736732b2-52bd-4041-b26f-a5a5cd81ef8d" width="500"/>
<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/e488c308-1467-480a-8742-af09f82d3c58" width="500"/>
<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/c392a1b6-44fc-468b-8cd4-1845d1f3c321" width="500"/>
<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/260304ee-3c64-44ac-866a-bd788776bb32" width="500"/>
<br><img src="https://github.com/droidecahedron/crowd-supply-2024/assets/380268/f613e711-4039-4b65-91e6-6341efe179a5" width="500"/>
