---
UID: NE:gnssdriver.__unnamed_enum_0
title: GNSS_DRIVERCOMMAND_TYPE (gnssdriver.h)
description: This enumeration indicates the type of driver command or configuration for the GNSS driver provided in the GNSS_DRIVERCOMMAND_PARAM structure.
old-location: gnss\gnss_drivercommand_type.htm
tech.root: gnss
ms.assetid: 61D7C52C-D8C9-4BBE-9DCA-B5E934A02FAE
ms.date: 05/14/2020
keywords: ["GNSS_DRIVERCOMMAND_TYPE enumeration"]
ms.keywords: GNSS_ClearAgnssData, GNSS_CustomCommand, GNSS_DRIVERCOMMAND_TYPE, GNSS_DRIVERCOMMAND_TYPE enumeration [Sensor Devices], GNSS_ForceOperationMode, GNSS_ForceSatelliteSystem, GNSS_ResetEngine, GNSS_ResetGeofencesTracking, GNSS_SetLocationNIRequestAllowed, GNSS_SetLocationServiceEnabled, GNSS_SetNMEALogging, GNSS_SetNiTimeoutInterval, GNSS_SetSuplVersion, GNSS_SetUplServerAccessInterval, gnss.gnss_drivercommand_type, gnssdriver/GNSS_ClearAgnssData, gnssdriver/GNSS_CustomCommand, gnssdriver/GNSS_DRIVERCOMMAND_TYPE, gnssdriver/GNSS_ForceOperationMode, gnssdriver/GNSS_ForceSatelliteSystem, gnssdriver/GNSS_ResetEngine, gnssdriver/GNSS_ResetGeofencesTracking, gnssdriver/GNSS_SetLocationNIRequestAllowed, gnssdriver/GNSS_SetLocationServiceEnabled, gnssdriver/GNSS_SetNMEALogging, gnssdriver/GNSS_SetNiTimeoutInterval, gnssdriver/GNSS_SetSuplVersion, gnssdriver/GNSS_SetUplServerAccessInterval
f1_keywords:
 - "gnssdriver/GNSS_DRIVERCOMMAND_TYPE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- gnssdriver.h
api_name:
- GNSS_DRIVERCOMMAND_TYPE
product:
- Windows
targetos: Windows
req.typenames: GNSS_DRIVERCOMMAND_TYPE
---

# GNSS_DRIVERCOMMAND_TYPE enumeration

## -description

This enumeration indicates the type of driver command or configuration for the GNSS driver provided in the [GNSS_DRIVERCOMMAND_PARAM](https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_drivercommand_param) structure.

## -enum-fields

### -field GNSS_SetLocationServiceEnabled

Informs the driver whether location is enabled on the device. This command is issued each time the location service is enabled/disabled on the device.

The associated command data is a **BOOL**.

Upon receiving this command set to FALSE the GNSS driver and GNSS device must:

- Stop any ongoing location sessions of any kind and from any HLOS application (if multiple applications are supported).

- If the GNSS device or driver does any operations in the background, for example, geofence tracking, assistance data refresh, etc., they should also be stopped. The GNSS adapter will stop all offloaded operations  when location is disabled.

In relation to location requests from the mobile operator:

- Location requests from the mobile operator for emergency location, to meet CALEA requirements, etc, should still be served regardless of the location switch status. These requests are expected to have the privacy override flag set or/and be initiated around the time of the user making an emergency call.

- Other network initiated location requests should honor the **GNSS_SetLocationNIRequestAllowed** command if this behavior is required by the mobile operator and implemented by the GNSS driver.

If the HLOS needs to initiate any new location request, for example, to enable the user to remotely find the device, the GNSS adapter will send a command to set the **GNSS_SetLocationServiceEnabled** to TRUE, initiate the fix session, and when the results are received it will send another command to set the **GNSS_SetLocationServiceEnabled** to FALSE:

- **GNSS_SetLocationServiceEnabled** set to TRUE=1-> Enabled

- **GNSS_SetLocationServiceEnabled** set to FALSE=0-> Disabled

Unless this command is issued by the GNSS adapter, the driver must assume that the location service is disabled on the system.

### -field GNSS_SetLocationNIRequestAllowed

Informs the driver if it is allowed to entertain network initiated location requests coming from the mobile network. The command only needs to be supported if required by the mobile operator. As of Windows 10, Microsoft is not aware of any mobile operator requiring this any longer, but this remains to avoid  any blocking issues during commercialization. If the command is not implemented, the GNSS driver should simply keep its default behavior.

The associated command data is a **BOOL**:

- **GNSS_SetLocationNIRequestAllowed** set to TRUE=1-> Allow

- **GNSS_SetLocationNIRequestAllowed** set to FALSE=0-> NotAllow

Unless this command is explicitly issued by the GNSS adapter, the driver must assume that the NI requests are enabled on the system.

The GNSS adapter maintains a system-wide state indicating whether NI requests are allowed. This state is determined by the location master switch (the setting that the user can toggle to turn location on or off) and a setting configured by the mobile operator to indicate if NI requests depend on the location master switch or not.

The GNSS adapter will evaluate the value of these two settings and will indicate to the GNSS driver if NI requests are allowed or not.

The location requests for emergency services or for CALEA (for example, the case of privacy override being set) must be served regardless of the value of this setting.

### -field GNSS_ForceSatelliteSystem

This command causes the GNSS driver to use the specified satellite system(s) for getting fixes. The parameter is a **DWORD** with the following values:

| Parameter | Value |
| --- | --- |
| GNSS_SATELLITE_ANY | 0x00 |
| GNSS_SATELLITE_GPS | 0x01 |
| GNSS_SATELLITE_GLONASS | 0x02 |
| GNSS_SATELLITE_BEIDOU | 0x04 |
| GNSS_SATELLITE_GALILEO | 0x08 |

0x10-0xFF are reserved.

This is expected to be used only for test purposes. Some mobile operators do require validations using a single satellite system.

### -field GNSS_ForceOperationMode

This command causes the GNSS driver to use the specified operation mode. The parameter is a **DWORD** with the following values:

| Parameter | Value |
| --- | --- |
| GNSS_OPERMODE_ANY | 0x00 |
| GNSS_OPERMODE_MSA | 0x01 |
| GNSS_OPERMODE_MSB | 0x02 |
| GNSS_OPERMODE_MSS | 0x04 |
| GNSS_OPERMODE_CELLID | 0x08 |
| GNSS_OPERMODE_AFLT | 0x10 |
| GNSS_OPERMODE_OTDOA | 0x20 |

0x40-0xFF are reserved.

This command is used for two purposes:

- To configure the mode of operation in the case of SUPL configuration. It is expected that mobile operators will only configure the device to work in Microsoft-based mode by which the SUPL service is used to obtain assistance data (**GNSS_OPERMODE_MSB**), or in standalone mode (**GNSS_OPERMODE_MSS**) in which the GNSS device can work really standalone or use assistance obtained from sources other than the SUPL service. The standalone mode is actually equivalent to the default mode (**GNSS_OPERMODE_ANY**).

- To configure different modes of operation for test purposes. This would mostly be used by mobile operators or OEMs for validation purposes.

Setting the SUPL **GNSS_ForceOperationMode** to **GNSS_OPERMODE_MSS** is an indication to the GNSS system to not do any kind of interaction with the SUPL server for AGNSS data.

### -field GNSS_ResetEngine

This command clears up the state of the GNSS engine. After this command is issued the engine will be ready for a cold start fix:

- All assistance data will be deleted.

- The almanac will persist.

- The GNSS engine configuration parameters will persist.

This command should only be called when there is no active fix session. This command is typically used for recursively testing the GNSS time to first fix on cold start.

### -field GNSS_ClearAgnssData

This command clears the AGNSS assistance data from the GNSS engine. This is used mainly for testing purpose to ensure that the driver requests for assistance data when a fix is requested. The associated command data contains the specific [GNSS_AGNSS_REQUEST_TYPE](https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ne-gnssdriver-gnss_agnss_request_type) enumeration to indicate the specific data element to be cleared:

- If **GNSS_AGNSS_TimeInjection** is specified, the time reference will be deleted in the GNSS engine. This may cause the GNSS engine to request again time injection.

- If **GNSS_AGNSS_PositionInjection** is specified, the coarse position reference will be deleted in the GNSS engine. This may cause the GNSS engine to request again coarse position injection.

- If **GNSS_AGNSS_BlobInjection** is specified, both ephemeris acquired from the satellites and any assistance blob injected will be deleted in the GNSS engine. This may cause the GNSS engine to request again an assistance blob.

It is highly recommended that this command is supported for test purposes even if the assistance data is not obtained from the OS location platform.

### -field GNSS_SetSuplVersion

This command sets the SUPL version that the mobile operator wants supported. The command data contains a value of [GNSS_SUPL_VERSION](https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_supl_version) structure which includes both the major and the minor SUPL versions indicated by the mobile operator. 

The SUPL client should use the SUPL version as specifies in the OMA SUPL standards, summarizing as follows:

- For network initiated scenarios, the SUPL INIT message from the H-SLP or E-SLP to the SET carries the intended SUPL major and minor version M1.m1 (normally the highest version supported by the SLP) in the version parameter. The SUPL INIT message also carries the minimum SUPL major version number M2 for which continuation of the session by the SET is possible in the minimum version parameter. The value of M2 will depend on the intended SUPL service – for example, for a single location fix M2 may be one; for triggered location M2 may be two. A SUPL session can be conducted between the SLP and the SET as long as the SET is using a SUPL major version between M2 and M1. The SET continues the SUPL session normally if it supports a major version M of SUPL between M2 and M1 (for example, M2 ≤ M ≤ M1) – and indicates this major version and a supported minor version m in the next message (for example, implicitly in the version parameter of the message).

- For SET initiated SUPL sessions, the initial SUPL message from the SET carries the supported SUPL major and minor version M1.m1 (implicitly in the version parameter). The H-SLP continues the session if it supports the same major version M1 and otherwise sends a SUPL END and terminates the session.

### -field GNSS_SetNMEALogging

This command sets the status for NMEA logging.

This command causes the GNSS driver to start/stop providing the data fix information via NMEA strings. The GNSS driver must continue providing fixes in the [GNSS_FIXDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_fixdata) structure.

The parameter is a **DWORD** with the following values:

| Parameter | Value |
| --- | --- |
| GNSS_NMEALOGGING_NONE | 0x00 |
| GNSS_NMEALOGGING_ALL | 0xFF |

The default value for this command is no NMEA logging. This command should not persist across system restart.

This command has been introduced to support OEM testing. This command is not used by the location framework or by Microsoft test tools.

### -field GNSS_SetUplServerAccessInterval

This command sets the minimum time in between requests to the server for assisted position to prevent service overload. The time interval is specified in seconds.

Mobile operators may use the configuration service provider to tune this setting, if they require it.  If this parameter is not supported, if can be ignored, but the SUPL configuration commands must not fail.

### -field GNSS_SetNiTimeoutInterval

This command sets how much time the device must wait for input from a user before it responds to the NI request executing the default action. The time interval is specified in seconds and the default value is 35 seconds. This timeout is 5 seconds larger than the timeout used by the operating system to wait for response from the user, and it is simply a failsafe in case of the operating system not responding. This command is applicable only to network initiated requests in which the verification from the user is requested. Mobile operators may use the configuration service provider to override the default value from the operating system. In such case the default values specified above should be replaced by the values provided by the mobile operator.

### -field GNSS_ResetGeofencesTracking

This command resets the geofence tracking operation. The GNSS driver must delete all geofences from the GNSS engine, stop geofence tracking and stop monitoring for signal conditions. The geofence tracking operation will begin as usual only when the HLOS creates one or more new geofences.

### -field GNSS_SetSuplVersion2

This command sets the SUPL 2 version for the GNSS driver.

### -field GNSS_CustomCommand

Range for custom IHV-specific GNSS commands:  0x0100 – 0x01FF.
