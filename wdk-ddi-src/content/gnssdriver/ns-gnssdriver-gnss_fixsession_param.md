---
UID: NS:gnssdriver.__unnamed_struct_9
title: GNSS_FIXSESSION_PARAM (gnssdriver.h)
description: This structure defines the parameters used by the GNSS adapter to start a fix session.
tech.root: gnss
ms.date: 06/16/2022
keywords: ["GNSS_FIXSESSION_PARAM structure"]
ms.keywords: "*PGNSS_FIXSESSION_PARAM, GNSS_FIXSESSION_PARAM, GNSS_FIXSESSION_PARAM structure [Sensor Devices], PGNSS_FIXSESSION_PARAM, PGNSS_FIXSESSION_PARAM structure pointer [Sensor Devices], gnss.gnss_fixsession_param, gnssdriver/GNSS_FIXSESSION_PARAM, gnssdriver/PGNSS_FIXSESSION_PARAM, sensors.gnss_fixsesson_param"
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
req.typenames: GNSS_FIXSESSION_PARAM, *PGNSS_FIXSESSION_PARAM
f1_keywords:
 - PGNSS_FIXSESSION_PARAM
 - gnssdriver/PGNSS_FIXSESSION_PARAM
 - GNSS_FIXSESSION_PARAM
 - gnssdriver/GNSS_FIXSESSION_PARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_FIXSESSION_PARAM
 - GNSS_FIXSESSION_PARAM
---

## -description

This structure defines the parameters used by the GNSS adapter to start a fix session.

## -struct-fields

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

Padding buffer reserved for future use.

### -field FixLevelOfDetails

Indicates the level of detail needed when the GNSS driver returns the fix information.

The GNSS driver may choose to override this input.

This flag is OR-ed with the bit-values defined in GNSS_FIXDETAIL_* mask.

### -field SingleShotParam

The [GNSS_SINGLESHOT_PARAM](/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_singleshot_param) structure defines the parameters for a single-shot fix session.

### -field DistanceParam

The [GNSS_DISTANCETRACKING_PARAM](/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_distancetracking_param) structure defines the parameters for a distance-based tracking fix session.

### -field ContinuousParam

The [GNSS_CONTINUOUSTRACKING_PARAM](/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_continuoustracking_param) structure defines the parameters for a continuous tracking fix session.

### -field LkgFixParam

The [GNSS_LKGFIX_PARAM](/windows-hardware/drivers/ddi/gnssdriver/ns-gnssdriver-gnss_lkgfix_param)  structure is not used currently by the system.

### -field UnusedParam

Padding buffer reserved for future use.

### -field Unused

Padding buffer reserved for future use.

## -remarks

The fix session parameters are different for different types of sessions. This structure contains a common set of parameters applicable for all fix sessions, followed by an overloaded structure (union) for each fix session type. The GNSS driver must use the appropriate structure from the union depending on the session type.
