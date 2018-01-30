---
UID: NS:gnssdriver.GNSS_FIXSESSION_PARAM
title: GNSS_FIXSESSION_PARAM
author: windows-driver-content
description: This structure defines the parameters used by the GNSS adapter to start a fix session.
old-location: sensors\gnss_fixsession_param.htm
old-project: sensors
ms.assetid: D51126FD-0448-487A-BD4E-170901E90B1E
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_FIXSESSION_PARAM structure [Sensor Devices], gnssdriver/GNSS_FIXSESSION_PARAM, *PGNSS_FIXSESSION_PARAM, GNSS_FIXSESSION_PARAM, PGNSS_FIXSESSION_PARAM structure pointer [Sensor Devices], sensors.gnss_fixsesson_param, gnssdriver/PGNSS_FIXSESSION_PARAM, PGNSS_FIXSESSION_PARAM, sensors.gnss_fixsession_param
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	gnssdriver.h
apiname:
-	GNSS_FIXSESSION_PARAM
product: Windows
targetos: Windows
req.typenames: "*PGNSS_FIXSESSION_PARAM, GNSS_FIXSESSION_PARAM"
---

# GNSS_FIXSESSION_PARAM structure


## -description


This structure defines the parameters used by the GNSS adapter to start a fix session.


## -syntax


````
typedef struct {
  ULONG               Size;
  ULONG               Version;
  ULONG               FixSessionID;
  GNSS_FIXSESSIONTYPE SessionType;
  ULONG               HorizontalAccuracy;
  ULONG               HorizontalConfidence;
  ULONG               Reserved[9];
  ULONG               FixLevelOfDetails;
  union {
    GNSS_SINGLESHOT_PARAM         SingleShotParam;
    GNSS_DISTANCETRACKING_PARAM   DistanceParam;
    GNSS_CONTINUOUSTRACKING_PARAM ContinuousParam;
    GNSS_LKGFIX_PARAM             LkgFixParam;
  };
  BYTE                Unused[512];
} GNSS_FIXSESSION_PARAM, *PGNSS_FIXSESSION_PARAM;
````


## -struct-fields




### -field SingleShotParam

The <a href="..\gnssdriver\ns-gnssdriver-gnss_singleshot_param.md">GNSS_SINGLESHOT_PARAM</a> structure defines the parameters for a single-shot fix session.


### -field DistanceParam

The <a href="..\gnssdriver\ns-gnssdriver-gnss_distancetracking_param.md">GNSS_DISTANCETRACKING_PARAM</a> structure defines the parameters for a distance-based tracking fix session.


### -field ContinuousParam

The <a href="..\gnssdriver\ns-gnssdriver-gnss_continuoustracking_param.md">GNSS_CONTINUOUSTRACKING_PARAM</a> structure defines the parameters for a continuous tracking fix session.


### -field LkgFixParam

The <a href="..\gnssdriver\ns-gnssdriver-gnss_lkgfix_param.md">GNSS_LKGFIX_PARAM</a>  structure is not used currently by the system.


### -field UnusedParam

 


### -field Size

Structure size.


### -field Version

Version number.


### -field FixSessionID

This is a unique identifier for a particular fix session.

 The GNSS adapter generates this number in a monotonically increasing order whenever a new fix session is requested. The number wraps around to zero. Given the lifetime of an active session and the number of possible parallel sessions even with multi-session support, the wrap-around is acceptable in this use case.

The GNSS driver must associate all fix related data to the original fix session by using the FixSessionID field. If the GNSS driver does not support multiple fix sessions, it may use the session ID of the last fix session request.


### -field SessionType

Identifies the type or recurrence type of this fix session.


### -field HorizontalAccuracy

The horizontal accuracy of the fix requested is only advisory information for the GNSS driver that can be used in an implementation-specific manner for making appropriate tradeoffs internally to satisfy the request.

A value of 0 indicates no particular accuracy is mandated by the GNSS adapter.


### -field HorizontalConfidence

The horizontal confidence is the circular confidence requested for this fix.

The platform expects fixes with a 95% confidence. The GNSS driver should honor this confidence value when it returns the fix and accuracy from the GNSS engine.


### -field Reserved

 


### -field FixLevelOfDetails

Indicates the level of detail needed when the GNSS driver returns the fix information.

The GNSS driver may choose to override this input.

This flag is OR-ed with the bit-values defined in GNSS_FIXDETAIL_* mask.


### -field Unused

 



#### - Reserved[9]

Reserved for future use.


#### - Unused[512]

Padding buffer.


## -remarks


The fix session parameters are different for different types of sessions. This structure contains a common set of parameters applicable for all fix sessions, followed by an overloaded structure (union) for each fix session type. The GNSS driver must use the appropriate structure from the union depending on the session type.


