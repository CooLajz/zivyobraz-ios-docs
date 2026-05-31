# Živý Obraz for iOS

[Česká verze](README.md)

A simple iOS app for a quick overview of devices from the [**Živý Obraz**](https://zivyobraz.eu/?page=o-sluzbe) service. On your iPhone or iPad, you can see the status of your e-paper devices, measured values, battery levels, history, and widgets directly on the Home Screen.

## Public Testing via TestFlight

The app is available for public testing via Apple's official TestFlight app. **Before opening the link, install Apple's TestFlight app from the App Store. Then open the link directly on your iOS device to connect it with TestFlight automatically.**

Test versions may contain bugs or unfinished behavior. When a new test version is released, TestFlight will notify you and offer an update; automatic updates may also be enabled.

**[Join the TestFlight test](https://testflight.apple.com/join/D6CzKtCZ)**

## Main Features

- **Overview of all devices** - temperature, humidity, battery, online status, and quick filtering of problems.
- **Home Screen widgets for iPhone and iPad** - choose a specific e-paper device and follow its values without opening the app.
- **Custom widgets for any values** - build your own card from any value available in the Živý Obraz service export.
- **Automatic data updates** - the app stores data for widgets and refreshes it in the background according to iOS capabilities.
- **Device detail** - signal, battery, firmware, last contact, and measurement history.
- **Multiple accounts and groups** - add multiple export keys and optionally filter devices by Group ID.
- **Dashboard customization** - custom aliases, device ordering, and hiding unused e-paper devices.
- **Optional device battery reporting** - the iOS device battery level can be sent back to Živý Obraz via the import API.
- **Shortcuts automation** - iOS Shortcuts actions can send device status or custom sensor values.

## App Screenshots

### Device Overview

The dashboard shows e-paper devices in clear cards. You can quickly see which devices are online, what their battery level is, and what values they are currently measuring.

<p>
  <img src="pics/hlavni_obrazovka_zarizeni.png" alt="Main screen with device list" width="280">
  <img src="pics/detail_zarizeni_1.png" alt="Device detail with history and diagnostics" width="280">
  <img src="pics/detail_zarizeni_2.png" alt="Device detail with additional information" width="280">
</p>

### Home Screen Widgets

Standard widgets show a specific e-paper device directly on the iPhone or iPad Home Screen. After loading data in the app for the first time, add the widget to the Home Screen and select a device.

<p>
  <img src="pics/widgety_na_plose.png" alt="Živý Obraz widgets on the Home Screen" width="560">
</p>

### Custom Widgets

Custom widgets are designed for values from the Živý Obraz service export. You can create a card for one dominant value, two or three values, or a list of multiple values.

<p>
  <img src="pics/hlavni_obrazovka_custom_widgety.png" alt="Custom widget overview in the app" width="280">
  <img src="pics/custom_widgety_nastaveni.png" alt="Custom card settings" width="280">
</p>

<p>
  <img src="pics/custom_widgety_na_plose.png" alt="Custom widgets on the iPhone or iPad Home Screen" width="560">
</p>

### App Settings

Settings are used to add accounts, export keys, an optional Group ID, and import API access for device battery reporting.

<p>
  <img src="pics/nastaveni_aplikace.png" alt="Account settings in the app" width="280">
</p>

## How to Set Up the App

### 1. Prepare an Export Key

Prepare an **export key** in the Živý Obraz service. The app uses it to load devices and values.

If you want to show only a selected group of devices, also prepare a **Group ID**. This step is optional.

### 2. Add an Account in the App

1. Open the Živý Obraz app.
2. Tap the settings icon.
3. Enter an account name.
4. Paste the export key.
5. Optionally enter a Group ID.
6. Save the settings using **Done**.

After saving, the app loads devices and stores data for widgets.

### 3. Add a Home Screen Widget

1. On the iPhone or iPad Home Screen, touch and hold an empty area.
2. Tap **Edit**, choose add widget, and search for **Živý Obraz**.
3. Select a widget size.
4. After adding the widget, touch and hold it and choose **Edit Widget**.
5. Select a specific device or keep automatic selection.

The widget uses the last loaded data and refreshes periodically according to iOS capabilities.

### 4. Create a Custom Widget

1. In the app, switch to the **Custom** section.
2. Tap the button to add a custom card.
3. Select values from the Živý Obraz service export.
4. Choose the card layout and appearance.
5. Add the **Živý Obraz Custom** widget to the Home Screen and select the created card in the same way as for a device widget in step 3.

A custom widget is useful for outdoor temperature, humidity, pressure, CO2, air quality, battery status, or any other value available in your export.

## Automation via iOS Shortcuts

The Živý Obraz app supports actions for the iOS Shortcuts app. This lets you automatically send data to the Živý Obraz service when different events happen on your phone.

Typical uses:

- send the battery status after connecting a charger,
- send the network name after connecting to Wi-Fi,
- send the phone's current IP address,
- send custom sensor values created directly in Shortcuts.

### Available Actions

You can find Živý Obraz actions in Shortcuts.

#### Send Device Status

This action sends the current phone status to accounts where device status reporting is enabled in the app.

It sends values such as:

- battery percentage,
- charging status.

This action is useful, for example, for an automation that runs when a charger is connected.

#### Add Sensor Value

This action creates one sensor value that can later be sent to Živý Obraz.

Fill in:

- sensor name,
- sensor value.

Example:

- sensor name: `WiFi`
- value: current Wi-Fi network name

This action does not send anything by itself. It only prepares the value for sending later.

#### Send Sensor Values

This action sends the prepared sensor values to the selected Živý Obraz account.

Fill in:

- account,
- sensor values.

If you use one or more "Add Sensor Value" actions before this action, the value should be filled into the sending action automatically. If it is not, set "Sensor Values" to the output of the last "Add Sensor Value" action.

### How to Send Multiple Sensors at Once

If you want to send multiple values, add several "Add Sensor Value" actions one after another and finish with one "Send Sensor Values" action.

Example:

1. Add Sensor Value  
   Name: `WiFi`  
   Value: current Wi-Fi network name

2. Add Sensor Value  
   Name: `IP`  
   Value: current IP address

3. Send Sensor Values  
   Account: selected Živý Obraz account  
   Sensor Values: output from the last "Add Sensor Value" action

Important: the last "Add Sensor Value" action does not contain only the last sensor. It contains the full collected list of previous sensors.

This means:

- the first "Add Sensor Value" action creates a list with one value,
- the second action takes the previous list and adds another value,
- the third action adds another value again,
- the "Send Sensor Values" action sends the complete resulting list.

### Empty Sensor Value

An empty value is not an error. If you send a sensor without a value, it is sent as an empty value.

This can be useful when some data is not available at that moment.

### Sensor Names

The sensor name is automatically converted to a safe format suitable for import into Živý Obraz when it is sent.

We recommend using simple names without special characters, for example:

- `WiFi`
- `IP`
- `Battery`
- `Mode`
- `Phone`

### Using Personal Automations

You can also use Živý Obraz actions in iOS personal automations.

For example:

1. Open the Shortcuts app.
2. Go to Automation.
3. Create a new personal automation.
4. Choose an event, for example "Charger".
5. Add a Živý Obraz action.
6. Configure the action as needed.
7. If iOS offers it, set the automation to run without confirmation.

This can send the current phone status to Živý Obraz immediately after connecting a charger, instead of waiting for a normal background update.

### Note About iOS Behavior

Automation execution is controlled by iOS. Depending on the phone settings, some automations may require confirmation or may be limited by the system.

The Živý Obraz app processes the action without requiring you to open the app manually, as long as iOS allows it in that situation.

## Automatic Updates

The app uses background refresh and a shared cache for widgets. iOS always decides exactly when the app or widget can refresh data, but the app tries to keep data fresh while avoiding unnecessary API calls.

For best results, open the app from time to time, keep Background App Refresh enabled, and perform a manual refresh after changing settings.

## Requirements

- iPhone or iPad with iOS/iPadOS 17 or newer.
- Export key from the Živý Obraz service.
- Import key from the Živý Obraz service for device battery reporting.

## Privacy and Keys

Export and import keys are stored securely in the iOS Keychain. Sensitive keys remain in the device keychain and, when sync is enabled, may be marked as shared so they are available on the user's devices signed in to the same Apple account. iCloud sync is optional, disabled by default, and enabled manually by the user. The app stores required settings, widget cache, device aliases, device order, and update diagnostics locally on the device, or in iCloud after this feature is enabled.

## Support

If you have a problem with the app, need help with setup, or want to suggest an improvement, please open a new issue in the project's GitHub repository:

**[Open a GitHub issue](https://github.com/CooLajz/zivyobraz-ios-docs/issues)**

When reporting a problem, please include the app version, iOS/iPadOS version, device model, a description of the issue, and steps to reproduce it. Do not include export or import keys in issue reports.

## Privacy Policy

This Privacy Policy applies to the **Živý Obraz** iOS app.

### Data Processed by the App

The app processes only the data required to display information from the Živý Obraz service:

- export keys and an optional Group ID used to load devices and values,
- an optional import key used to send the iOS device battery level, device status, or custom sensor values to the Živý Obraz service,
- account names entered by the user,
- device lists, measured values, battery status, online status, and other information returned by the export API,
- values created by the user in iOS Shortcuts, if the user sends them using Živý Obraz actions,
- app settings, device aliases, device order, hidden items, custom widgets, and widget cache,
- technical information needed for update diagnostics inside the app.

### Data Storage

Export and import keys are stored in the iOS Keychain. Sensitive keys remain stored in the device keychain; if the user enables iCloud sync, they may be marked as shared so they are available on the user's devices signed in to the same Apple account. Other settings and cache data are stored locally on the device and in the shared storage used by the app and its widgets.

iCloud sync is optional, disabled by default, and enabled manually by the user inside the app. After it is enabled, the app may store settings and app data in the user's iCloud so they can sync between the user's devices and be restored after reinstalling the app.

iCloud data is managed by Apple as part of the user's Apple account. The app does not send this data to the app developer's own servers and does not use it for advertising or analytics.

### Communication with the Živý Obraz Service

The app uses the keys entered by the user to communicate with the Živý Obraz API. When loading data, the app sends the export key and, if configured, the Group ID so it can retrieve devices and values available for the account. If the user enables optional device status reporting or uses Shortcuts actions, the app may use the import key to send the current iOS device battery level, charging status, or custom sensor values to the Živý Obraz service.

Data processing performed by the Živý Obraz service is governed by the terms and privacy policy of that service.

### Data Sharing

The app does not sell, rent, or share personal data with third parties. The app does not include advertising SDKs, tracking SDKs, or third-party analytics tools.

### User Rights

The user can remove data stored by the app by deleting accounts, clearing saved settings, or uninstalling the app. Removing an account deletes the stored keys and app data related to that account. Data stored in iCloud can also be managed in the Apple account and iCloud settings.

### Changes to This Policy

This policy may be updated when the app features or data processing practices change. The latest version is available on this page.

### Contact

For privacy-related questions, please use the contact information provided for the app in the App Store or in the project repository.
