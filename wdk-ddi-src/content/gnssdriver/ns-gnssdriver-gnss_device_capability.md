---
UID: NS:gnssdriver.__unnamed_struct_2
title: GNSS_DEVICE_CAPABILITY (gnssdriver.h)
description: The GNSS_DEVICE_CAPABILITY structure is used to determine the device capabilities of the underlying GNSS engine.
tech.root: gnss
ms.date: 06/20/2022
keywords: ["GNSS_DEVICE_CAPABILITY structure"]
ms.keywords: "*PGNSS_DEVICE_CAPABILITY, GNSS_DEVICE_CAPABILITY, GNSS_DEVICE_CAPABILITY structure [Sensor Devices], PGNSS_DEVICE_CAPABILITY, PGNSS_DEVICE_CAPABILITY structure pointer [Sensor Devices], gnss.gnss_device_capability, gnssdriver/GNSS_DEVICE_CAPABILITY, gnssdriver/PGNSS_DEVICE_CAPABILITY"
req.header: gnssdriver.h
req.include-header: Gnssdriver.h
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
req.typenames: GNSS_DEVICE_CAPABILITY, *PGNSS_DEVICE_CAPABILITY
f1_keywords:
 - PGNSS_DEVICE_CAPABILITY
 - gnssdriver/PGNSS_DEVICE_CAPABILITY
 - GNSS_DEVICE_CAPABILITY
 - gnssdriver/GNSS_DEVICE_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_DEVICE_CAPABILITY
 - GNSS_DEVICE_CAPABILITY
---

## -description

The **GNSS_DEVICE_CAPABILITY** structure is used to determine the device capabilities of the underlying GNSS engine.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field SupportMultipleFixSessions

Indicates whether the GNSS driver natively supports multiple sessions for the same type (For example, multiple simultaneous distance tracking sessions initiated by the HLOS). If FALSE, the GNSS adapter will multiplex  the fix session requests from multiple LBS apps to combine into one fix session request that satisfies all the client requests.

If this capability is not present, the driver must support at least one active sessions of each supported fix session type. For example, if the driver supports distance-based tracking and single-shot functionality, it must support one distance-based fix session and one single-shot fix session active at the same time.

The driver must always support modification of session parameter for an active fix session type so that the GNSS adapter does not need to stop/start an ongoing fix session when a new fix request needs to be multiplexed. In Windows 10, the GNSS adapter does not support initiating in the GNSS driver multiple sessions of the same type.

### -field SupportMultipleAppSessions

Indicates whether the GNSS driver natively supports and tracks requests coming from multiple HLOS applications. The GNSS driver must not restrict being called from more than one application at the same time.

A value of TRUE indicates that the driver keeps track of the different HLOS application sessions, logically partitions the requests, ensures that request from one application session does not influence another application session, and so on. For example, it will be able to handle separately the GNSS adapter and a test application, and respond to commands from each separately.

A value of FALSE indicates that the driver does not differentiate different HLOS application sessions and logically treats everything in a global manner as if they all are coming from a single HLOS application-session.

### -field RequireAGnssInjection

Indicates whether the GNSS driver requires assistance data to be injected for faster TTFF.

### -field AgnssFormatSupported

Specifies a bitmask containing the different AGNSS formats (GNSS_AGNSSFORMAT_*) that the driver can handle.

```cpp
#define GNSS_AGNSSFORMAT_XTRA1      0x01
#define GNSS_AGNSSFORMAT_XTRA2      0x02
#define GNSS_AGNSSFORMAT_LTO        0x04
#define GNSS_AGNSSFORMAT_XTRA3      0x08
#define GNSS_AGNSSFORMAT_XTRA3_1    0x10
#define GNSS_AGNSSFORMAT_XTRA3_2    0x20
#define GNSS_AGNSSFORMAT_XTRA_INT   0x40
```

The values 0x0080-0xFFFF are  reserved for extensibility.

This list currently includes a few IHV proprietary formats. The list can be updated when IHVs or OEMs decide to obtain the GNSS assistance information, specifically extended ephemeris, via the location platform.

### -field AgnssFormatPreferred

Specifies the preferred AGNSS format using the same bitmask as AgnssFormatSupported. For example, if both XTRA1 and XTRA2 are supported but XTRA2 is the preferred format, the GNSS driver sets AgnssFormatSupported to 0x000C and AgnssFormatPreferred to 0x0004.

### -field SupportDistanceTracking

Indicates whether the GNSS driver/engine natively supports low-power tracking of the device based on a session-specific threshold. A TRUE value implies that the driver can support this natively in a low-power mode, for example, by offloading the tracking to a low-power processor and not requiring the app processor to be up and poll for movement.

If the GNSS driver supports distance tracking, it implicitly supports other types of parallel fix sessions at the same time. For example, if a distance tracking session is active, a parallel single-shot must also be allowed and both types of fix sessions must be honored.

### -field SupportContinuousTracking

Indicates whether the GNSS Driver/Engine natively supports continuous low-power tracking of the device. A TRUE value implies that the driver can support this natively in a low-power mode, for example, by offloading the tracking to a low-power processor and not requiring the app processor to be up and poll continuously.

If the GNSS Driver supports continuous tracking, it implicitly supports other types of parallel fix sessions at the same time. For example, single-shot and continuous tracking can happen in parallel.

### -field Reserved1

Reserved for future use.

### -field Reserved2

Reserved for future use.

### -field Reserved3

Reserved for future use.

### -field Reserved4

Reserved for future use.

### -field Reserved5

Reserved for future use.

### -field GeofencingSupport

Version 1 GNSS drivers must indicate that this capability is not supported.

Version 2 GNSS drivers and later can indicate geofence support by setting the following bitmasks:

```cpp
#define GNSS_GEOFENCESUPPORT_SUPPORTED     0x01
#define GNSS_GEOFENCESUPPORT_CIRCLE        0x02
```

GNSS_GEOFENCESUPPORT_SUPPORTED indicates that the GNSS engine supports geofence tracking. Supporting geofence tracking functionality implies that it is done natively, in a power-optimized way, and uses the appropriate hybrid positioning technologies available in the GNSS engine, as applicable.

GNSS_GEOFENCESUPPORT_CIRCLE indicates that the GNSS engine supports circular geofences.

### -field Reserved6

Reserved for future use.

### -field Reserved7

Reserved for future use.

### -field SupportCpLocation

Specifies whether CP location is supported.

### -field SupportUplV2

Specifies whether V2 user plane location for CDMA is supported.

### -field SupportSuplV1

Specifies whether SUPL V1 is supported.

### -field SupportSuplV2

Specifies whether SUPL V2 is supported.

### -field SupportedSuplVersion

Specifies the latest SUPL version that is supported by the SUPL client. This version information is currently not used by the HLOS at for any validation purposes.

### -field MaxGeofencesSupported

Specifies the number of geofences the GNSS engine can track based on constraints set by the platform. This value will only be valid when the GeofencingSupport field is set.

### -field SupportMultipleSuplRootCert

Specifies the SUPL parameter.

### -field GnssBreadCrumbPayloadVersion

Must be BREADCRUMBING_UNSUPPORTED or BREADCRUMBING_VERSION_*x*.

### -field MaxGnssBreadCrumbFixes

Must greater than or equal to MIN_BREADCRUMBS_SUPPORTED.

### -field Unused

Padding buffer reserved for future use.

## -remarks

This is a list of individual capability support. The capability is represented either by a Boolean or by a well-defined enumeration of the specific attribute.
