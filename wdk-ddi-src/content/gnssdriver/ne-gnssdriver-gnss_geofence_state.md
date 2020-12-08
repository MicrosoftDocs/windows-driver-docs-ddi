---
UID: NE:gnssdriver.__unnamed_enum_3
title: GNSS_GEOFENCE_STATE (gnssdriver.h)
description: GNSS_GEOFENCE_STATE enumerates the various states of a single geofence.
old-location: gnss\gnss_geofence_state.htm
tech.root: gnss
ms.date: 11/03/2020
keywords: ["GNSS_GEOFENCE_STATE enumeration"]
ms.keywords: GNSS_GEOFENCE_STATE, GNSS_GEOFENCE_STATE enumeration [Sensor Devices], GNSS_GeofenceState_Entered, GNSS_GeofenceState_Exited, GNSS_GeofenceState_Unknown, gnss.gnss_geofence_state, gnssdriver/GNSS_GEOFENCE_STATE, gnssdriver/GNSS_GeofenceState_Entered, gnssdriver/GNSS_GeofenceState_Exited, gnssdriver/GNSS_GeofenceState_Unknown
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: GNSS_GEOFENCE_STATE
f1_keywords:
 - GNSS_GEOFENCE_STATE
 - gnssdriver/GNSS_GEOFENCE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - GNSS_GEOFENCE_STATE
---

# GNSS_GEOFENCE_STATE enumeration

## -description

GNSS_GEOFENCE_STATE enumerates the various states of a single geofence.

## -enum-fields

### -field GNSS_GeofenceState_Unknown

The state of the geofence is unknown.

### -field GNSS_GeofenceState_Entered

The geofence has been entered.

### -field GNSS_GeofenceState_Exited

The geofence has been exited.

## -remarks

The following bitmasks are used by the HLOS to request state-change alerts for geofences:

```cpp
#define GNSS_GEOFENCEALERTTYPE_ENTRY  GNSS_GeofenceState_Entered    // Enter Geofence
#define GNSS_GEOFENCEALERTTYPE_EXIT   GNSS_GeofenceState_Exited     // Exit Geofence
```

An entry alert is raised when the previous state of the geofence was unknown or exited and the device has now entered the geofence.

An exit alert is raised when the previous state of the geofence was entered and the device has now exited the geofence. If the previous state of the geofence was unknown, and the device is currently outside of the geofence, no exit alert will be generated.

The location platform only sends an exit trigger to apps when the previous known state for a fence is inside the fence. This is a design decision to avoid chattiness of exit events on geofence configuration (For example, when not expecting a user configuring an exit fence from home to need to be notified that they are outside of home if they configure the notification when they are already outside of the home). Nevertheless, the location platform could handle where the GNSS driver sends exit events, but it is not recommend because then the interaction between the GNSS adapter and the GNSS driver will become very verbose. Given that the chances of the user entering a geofence are much smaller than the user being outside a geofences, this behavior reduces the required interaction between the GNSS driver and the GNSS adapter. For example, in the  case of 100 geofences pushed to the GNSS driver, and a user was outside all of them, without this behavior the will need to send to the GNSS adapter 100 exit notifications. The likelihood of something similar to this happening for entry events is very small.

The geofence state transition and the associated alerts are shown below. For simplicity, the hysteresis and geofence boundary conditions are implied.

![GNSS geofence state diagram](images/geofence-entry-exit.png)

The key aspects of this state diagram are:

- No alert is to be raised when transitioning from GNSS_GeofenceState_Unknown to GNSS_GeofenceState_Exited state.

- When the GNSS engine is unable to track any geofences at all, a single global tracking status alert needs to be raised, as opposed to one alert for each geofence. The GNSS engine could maintain the last know state for each fence instead of transitioning to GNSS_GeofenceState_Unknown state, so that when it is able to track again, the needed geofence alerts can be raised based on the new entry/exit detection.

  Maintaining this last known state is not currently necessary though, because once the GNSS driver raises the event with gnss_geofences_tracking_status as FAILURE, the location platform in the HLOS will start doing the geofences tracking. During this time, the GNSS engine should continue to check, in a power optimized way, if geofences can be tracked again. The IHV can use optimizations to make this detection at low power. Common techniques for optimization include the following:

  - Progressive back-off

  - Waiting for low-cost signals that are indicative of device movements such as accelerator data or cellular/WiFi change notifications.

  - Requesting a low-accuracy distance tracking session from the HLOS using the public Geolocation WinRT APIs.

  - Low power checks for satellite signal.

  When GNSS engine is able to track geofences again, it communicates so by setting the gnss_geofence_tracking_status as SUCCESS to GNSS adapter/HLOS

  The GNSS adapter will issue GNSS_ResetGeofenceTracking commands and re-add currently active geofences with current entry/exit criteria of each geofence. This needs to be done in case the set of geofences to be tracked has changed or in the state for any geofence has changed.
