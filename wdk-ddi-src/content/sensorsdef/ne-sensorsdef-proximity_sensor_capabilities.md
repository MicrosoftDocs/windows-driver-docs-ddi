---
UID: NE:sensorsdef.PROXIMITY_SENSOR_CAPABILITIES
tech.root: sensors
title: PROXIMITY_SENSOR_CAPABILITIES
ms.date: 02/26/2024
targetos: Windows
description: The PROXIMITY_SENSOR_CAPABILITIES enumeration values indicate the capabilities of a proximity sensor.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: sensorsdef.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sensorsdef.h
api_name:
 - PROXIMITY_SENSOR_CAPABILITIES
f1_keywords:
 - PROXIMITY_SENSOR_CAPABILITIES
 - sensorsdef/PROXIMITY_SENSOR_CAPABILITIES
dev_langs:
 - c++
helpviewer_keywords:
 - PROXIMITY_SENSOR_CAPABILITIES
---

# PROXIMITY_SENSOR_CAPABILITIES enumeration (sensorsdef.h)

## -description

The **PROXIMITY_SENSOR_CAPABILITIES** enumeration values indicate the capabilities of a proximity sensor.

## -enum-fields

### -field Proximity_Sensor_Human_Presence_Capable

The sensor can detect human presence.

### -field Proximity_Sensor_Human_Engagement_Capable

The sensor can detect if the user is engaged with the system.

### -field Proximity_Sensor_Human_Head_Azimuth_Capable

The sensor can detect the azimuth of the user's head.

### -field Proximity_Sensor_Human_Head_Altitude_Capable

The sensor can detect the altitude of the user's head.

### -field Proximity_Sensor_Human_Head_Roll_Capable

The sensor can detect the roll of the user's head.

### -field Proximity_Sensor_Human_Head_Pitch_Capable

The sensor can detect the pitch of the user's head.

### -field Proximity_Sensor_Human_Head_Yaw_Capable

The sensor can detect the yaw of the user's head.

### -field Proximity_Sensor_Human_Identification_Capable

The sensor can identify a person.

### -field Proximity_Sensor_Multi_Person_Detection_Capable

The sensor can detect if more than one person is present.

### -field Proximity_Sensor_Supported_Capabilities

Indicates that all capabilities are supported.
