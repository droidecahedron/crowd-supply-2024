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
- nRF Connect SDK
    - nRF CLI Tools (🔗 [Link](https://www.nordicsemi.com/Products/Development-tools/nRF-Command-Line-Tools/Download?lang=en#infotabs))
    - VS Code Extension Pack
        - Toolchain - select v.2.6.1
        - SDK - select v.2.6.1
        - These are large downloads and take a long time. Please complete before the workshop.

- Also install
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
- Click Open:
- ![Teardown 2024 Nordic Semiconductor Workshop_html_1ed5f82c](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/be469b34-96e5-41d3-93b1-8b76191241c5)

## Under Applications at the bottom of the left pane 
- Click on Add build configuration 
- Select the “thingy91_nrf9160_ns” board
- Click Build Configuration 
- ![Teardown 2024 Nordic Semiconductor Workshop_html_915e339e](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/383b05dc-9d52-4514-ac83-f7b59f3881c2)

## Launch nRF Connect for Desktop 
- Click on the Programmer app
- ![Teardown 2024 Nordic Semiconductor Workshop_html_87672769](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8958ac27-c970-4f15-b830-521fb954d9d6)

## On your Thingy:91: 
- Turn it off 
- Hold down the center button 
- Turn it on then release the center button --> it is now in MCUboot mode (USB/serial bootloader) 
- Connect it to your notebook with a micro USB cable

## In the Programmer app: 
- Click on Add file 
- Navigate to crowd-supply-2024/base/build/zephyr 
- Select app_signed.hex 
- Click on Select Device 
- Select Nordic Thingy:91
- ![Teardown 2024 Nordic Semiconductor Workshop_html_190467b3](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/b2cda5af-d629-402f-b344-554e043c54b2)
- Click Write
- Click Write again
- The app will now program the device.
- ![Teardown 2024 Nordic Semiconductor Workshop_html_5cc38ae3](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/ef736442-0a70-4cfa-9102-e99f01aa2c65)
- ![Teardown 2024 Nordic Semiconductor Workshop_html_873076b9](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8e2644fd-9310-40f7-9ee3-723f3df4448c)
- ![Teardown 2024 Nordic Semiconductor Workshop_html_6e0fd4e8](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8440f326-0cc4-427f-9be9-aa899a97bf24)

## Create your nRF Cloud account:
- Open a browser to: https://nrfcloud.com([Link](https://nrfcloud.com))
- Click Register
- ![Teardown 2024 Nordic Semiconductor Workshop_html_19ef473f](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/9124ac0a-7dce-4a3d-b00d-d34264cd05ee)
- Fill out the form.
- ![Teardown 2024 Nordic Semiconductor Workshop_html_bd9bc174](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/c644e7b0-2ecf-4379-844e-231d008ee844)
- Click Create Account.
- Receive confirmation code vial email.
- Confirm the code.
- ![Teardown 2024 Nordic Semiconductor Workshop_html_73d9d0ed](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/8b023421-6171-4cbb-ba5d-f0ece6449769)

## Register your SIM card:
- Click on Device Management --> SIM Cards
- Click Add SIM.
- Fill out the form.
- Click Activate SIM.
- Follow any additional instructions.
- ![Teardown 2024 Nordic Semiconductor Workshop_html_6d61ade0](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/04caff91-8451-475c-81b9-7d8f8694e5cb)
- Remove your Thingy:91 from its orange cover.
- Remove the SIM from the carrier and insert into the SIM slot on your Thingy:91.

## Add your Thingy:91 to your account:
- Click on Device Management --> Devices.
- Click Add Devices.
- Click LTE Device.
- Fill out the form with info from the white sticker.
-  ![Teardown 2024 Nordic Semiconductor Workshop_html_85ba2cf](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/bd1f27ff-1673-4750-b9fa-52c1b1aaffd8)
-  ![Teardown 2024 Nordic Semiconductor Workshop_html_3ec93092](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/6028e6c9-3bf4-43db-85ca-8ba9b520f35d)
- Your device should now be connected to your nRF Cloud account.
- ![Teardown 2024 Nordic Semiconductor Workshop_html_611cbd60](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/a7d967c0-a04b-499a-805c-b3091363a0b0)
- Take a tour of this page.
- While your device is running, it generates log messages, which you can view using Serial Terminal.
- ![Teardown 2024 Nordic Semiconductor Workshop_html_f29f0e8f](https://github.com/droidecahedron/crowd-supply-2024/assets/380268/cfc04dc6-ecee-4631-af49-1a6b56098ffd)

# Customizing the sample for solving puzzles
## Add a button handler in application.c
- In VSCode, in the Explorer, view the source for `prj.conf`. 
- Add: `CONFIG_DK_LIBRARY=y` 
- View the source for `application.c`. 
- Add: `#include <dk_buttons_and_leds.h>` 
- Add a call in `main_application_thread_fn()` to `dk_buttons_init(button_handler);`
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
- In the Programmer app, hit Reload files. Place your Thingy:91 back in MCUboot mode, then click Write. 
- In Serial Terminal, and watch the log output. 
- Look for log messages when you press the button. 

  








