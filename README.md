# Hue Controller

A single-file web app for controlling a Philips Hue system from your browser over the local network.

## Features

- **Bridge discovery** — auto-discovers your Hue Bridge on the local network, or enter the IP manually
- **Light control** — toggle lights on/off and adjust brightness for each bulb individually
- **All On / All Off** — control all reachable lights at once
- **Automations** — schedule lights to turn on or off based on:
  - A specific time each day
  - Sunrise or sunset (with a configurable minute offset), auto-updating daily using your location
- Credentials and automations persist between sessions via `localStorage`

## Usage

1. Open `index.html` directly in a browser on the **same local network as your Hue Bridge**
2. Click **Discover** to find your bridge automatically, or enter its IP address manually
3. Press the physical button on your Hue Bridge, then click **Link App** within 30 seconds
4. Control your lights from the **Lights** tab, and set up schedules in the **Automations** tab

> **Note:** Automations only fire while the page is open in the browser. No server or install required.

## Sunrise / Sunset Automations

1. Go to the **Automations** tab and set your location (browser geolocation or manual lat/lng)
2. Create an automation and choose **Sunrise** or **Sunset** as the trigger
3. Optionally set a minute offset (e.g. `-30` = 30 minutes before sunset)
4. Sun times are fetched daily from [sunrise-sunset.org](https://sunrise-sunset.org/api) and cached per session

## Tech

Plain HTML, CSS, and JavaScript — no build step, no dependencies.

- Hue API v1 (CLIP v1) over HTTP on the local network
- [sunrise-sunset.org](https://sunrise-sunset.org/api) for daily sun times
- [discovery.meethue.com](https://discovery.meethue.com) for bridge auto-discovery
