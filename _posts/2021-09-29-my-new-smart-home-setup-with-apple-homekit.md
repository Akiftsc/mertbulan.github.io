---
title: My new smart home setup with Apple HomeKit
image: /uploads/apple-homekit-setup.png
category: bests
date: 2021-09-29 15:12
---

![Apple HomeKit setup](/uploads/apple-homekit-setup.png)

Almost a year ago, I wrote a blog post about [my smart home setup with Raspberry Pi and Home Assistant](https://mertbulan.com/2020/12/20/my-smart-home-setup-with-raspberry-pi-and-home-assistant/). Since then, I have had some issues with my setup and I decided to create a new smart home setup with Apple HomeKit. I would like to share why I decided to switch to Apple HomeKit and talk about my new setup.

### Raspberry Pi and HomeAssistant

One of the first issues in my setup was that it wasn't recognizing my iPhone and trigger the automation based on my iPhone's location (or connection to the Wi-Fi). I had some automation such as turn on the lights when I arrive home if it is sunset, turn off the lights when I leave home. That automation stopped working after some time and it was annoying. 

Another problem was that after a few days of using the setup, I wasn't able to access the UI and to the Pi via SSH. I always had to restart the device. The biggest problem happened when the SD Card in the Pi was out of storage because of the logs. Seems like I was logging everything so the logs got bigger and bigger and then the hub stopped working. After that, I had to set up the hub and all the connected devices from scratch.

After some time, I realized that I am spending too much time dealing with those problems. In the beginning, I knew that if I want to create my hub, I will need to spend some time but I wasn't expecting that I will need to spend more after completing the setup. In the end, I decided to create a new smart home setup with Apple HomeKit.


### New Setup

On my previous setup, the hub was Raspberry Pi, and devices were connected via Wi-Fi or Zigbee. For my new setup, I decided to buy an Apple TV 4K. You can also buy an iPad or a HomePod mini and use them as your HomeKit hub but I wanted to go with Apple TV because I wasn't happy with my TV's interface and I know that most of the TV manufacturers are spying on what we are watching.

After buying an Apple TV, I started to buy new devices and sensors because none of my previous devices and sensors were compatible with Apple HomeKit.

#### Heating

For my smart home setup, the most important thing for me is the smart radiator valve. Because this device is helping me to save energy and money. For that one, I picked [Eve Thermo Smart Radiator Valve](https://www.evehome.com/en/eve-thermo). Eve is a German company and they care about privacy. If you look at the thermostat market, you will probably see some brands like [tado](https://www.tado.com/de-en/) and when you visit their homepage, you won't even see `privacy` word there. Their products are connected to their servers and they try to sell you some subscriptions. Eve doesn't do those kinds of things and everything works in your network. You don't even need to create an account for their app.

Their app, Eve, is super nice. You can create multiple timeframes for when you want to turn on the heater. One problem that I was having with my previous smart radiator valve, AVM FRITZ!DECK 301, when you turn off/on the device from HomeAssistant, it was taking around 15 minutes to make the change in the device. This was a big issue for me because when you open the window for just 10 minutes, then the device is not going to turn itself off and you will waste energy. Eve Thermo receives the changes almost instantly so this also helped me to set up new automation with a window contact sensor.

Since I was happy with Eve's valve, I decided to buy Eve's [Window & Door Contact Sensor](https://www.evehome.com/en/eve-door-window) for the window in my living room. I created very simple automation that turns off the heater if I open the window and turns on the heater if I close the window. Of course, this automation also checks the time frame that I normally turn on the heater (09:00-19:00) in my living room.

#### Lights

Since my lights are not smart, I am making them smart by using smart sockets. There are a lot of smart sockets but since I was planning to buy multiple ones, I decided to go with the most affordable brand, [Meross](https://meross.com/Detail/58/Smart%20Wi-Fi%20Plug%20Mini). I would be happy to go with Eve's smart socket but it costs 38€ and I bought 4 smart sockets from Meross for 50€ (12,50€ per socket). I used two of them for the lights (one in my bedroom, one in my living room), one for [my MUJI fan](https://www.muji.eu/pages/online.asp?PID=9739&qclr=4550002435752) in the living room and one for the security camera.

#### Security

I changed my job in June and I started to work fully remote. I decided to have a proper working setup and for that, I spent some money. Also, I realized that I have too many expensive electronics at home. So, both for the security of the company's properties and my electronic devices, I decided to buy a security camera. Of course, my main purpose to have a camera is not trying to catch the thief but scaring the thief so I don't need to deal with my insurance and set up everything again.

One of my friends suggested me VOCOlinc's security camera. VOCOlinc is a company based in Shenzhen, China and they are producing smart home devices that are compatible with Apple HomeKit. They are affordable comparing to their competitors. After my friend's suggestion, I bought [Opto Smart Indoor Camera](https://www.vocolinc.com/products/opto-smart-indoor-camera-vc1-us). The camera looks nice but VOCOlinc's app's user interface is not that good. You can place the camera on a desk or you can hang it. So it supports both orientations. I hang it to the ceil of the hallway to see the entrance door. Since the camera has a motion sensor, if the door opens, I get a notification and it starts recording a video. You can upload the video to iCloud if you want. Since Apple allows the lowest tier of iCloud+ subscription (it costs 0,99€/month) to connect one camera, you can save the recorded video to your iCloud account. That's what I am doing.

On the Apple Home app, you can have two recording settings: when I am at home, turn off the camera and when I leave home, start streaming and recording. With these two settings, you never stream video while you are at home so it is nice for privacy. VOCOlinc also has a privacy mode in their app but it is not accessible in the Home app. If you enable it, the camera looks down so it doesn't see anything. If you want, you can create a Siri Shortcut but that requires manual interaction with the notification that you will receive when you leave home. I thought I can make the camera more privacy-focused by connecting one of the smart sockets to the camera. So I can also turn off the socket if I am at home to make sure that the camera is not streaming anything. After trying this setup, I saw that the camera is resetting its head's position when you power it off. So when you power it on again, the camera doesn't look at the place that you set up before. So, for now, I am just relying on recording options setting on the Home app.

One of the cool things about the camera is that you can connect to the automation. If the camera detects motion, you can turn on the lights and Apple TV and start playing music. It is a nice way to scare the thief :)

#### Sensors

After reading the effect of the CO2 level in the room on your productivity ([study 1](https://ehp.niehs.nih.gov/doi/full/10.1289/ehp.1510037#:~:text=Results%3A,independently%20associated%20with%20cognitive%20scores.), [study 2](https://journals.sagepub.com/doi/full/10.1177/0143624418790129)), I decided to buy a sensor that also measures the CO2 level in my living room (where I work). For that, I couldn't find too many alternatives and decided to buy [Qingping Air Monitor Lite](https://www.qingping.co/air-monitor-lite/overview) since it has HomeKit support. It measures CO2, temperature, humidity, PM2.5, PM10 in the room. For now, I couldn't connect it to any automation and I also realized that I can't set up notifications for some scenarios like if the CO2 level goes above 1000ppm or if the humidity level goes above 80%, etc. I guess this is related to the Home app and I hope Apple allows us to set up this kind of notification in the future.

Another thing that I realized, on the climate screen of the Home app, you see humidity, temperature, and air quality but not CO2 level. You have to visit the living room screen to see and tap the Carbon Dioxide Sensor icon to see the CO2 level. This is another thing to fix for Apple.


### Automation

Managing automation on the Home app is way easier than managing them on HomeAssistant. Right now, these are the automation that I have:

- When I am home, if it is sunset, turn on the lights
- When I arrive home, if it is sunset, turn on the lights
- When I leave home, if the lights are on, turn off the lights
- When I leave home, turn off the heaters
- When I leave home, start streaming and allow recording for the camera
- When I arrive home, stop streaming for the camera
- When I open the window (between 09:00-19:00), turn off the heater
- When I close the window (between 09:00-19:00), turn on the heater
- If the camera detects motion, start recording a video and send me a notification
- When I say "Good Night" to Siri, turn off the lights


### Cost

My previous smart home setup cost me 255,34€. This time, it cost me more but if I think about the experience that I have right now, I can easily say that it is worth it. 

|Item|Price|
|----|-----|
|Apple TV 4K|219,00€|
|2 x Eve Thermo|119,80€|
|4 x Meross Smart Socket|49,99€|
|VOCOlinc Camera|48,99€|
|Qingping Air Monitor Lite|108,60€|
|----|-----|
|**Total**|**546,38€**|


Since I don't need the previous devices and sensors because they don't support HomeKit, I sold them on eBay with little discount.

In the end, I have a sensor that measures CO2 level, I have an Apple TV that has a much better TV experience, I also got 1 year of Apple TV+ subscription (worth around 60€) and as an extra, I have a security camera comparing to my previous smart home setup.


### What's next?

Since days are getting shorter and I started to wake up when the sun is not raised, I would like to buy a smart blind. For that, I am waiting for [Eve Motionblinds](https://motionblinds.com/eve/) to be available since I couldn't find a smart blind that supports Apple HomeKit without buying a gateway.

Besides that, I am going to buy another Eve Window & Door Contact Sensor and another Qingping Air Monitor Lite for my sleeping room. 

The last thing that I would like to have is a device that opens my windows automatically. So, I can maybe create an automation based on the CO2 level in the room. So far I couldn't find anything on the market. I will wait for one or I am going to try to build my own. 

