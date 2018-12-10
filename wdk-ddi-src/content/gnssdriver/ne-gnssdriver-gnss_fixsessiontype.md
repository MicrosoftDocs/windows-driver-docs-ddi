---
UID: NE:gnssdriver.__unnamed_enum_1
title: GNSS_FIXSESSIONTYPE
author: windows-driver-content
description: This enumeration indicates the type of location fix needed by the GNSS adapter when it issues an IOCTL_GNSS_START_FIXSESSION control code. This enumeration is set within the GNSS_FIXSESSION_PARAM structure.
old-location: gnss\gnss_fixsessiontype.htm
tech.root: gnss
ms.assetid: CE611168-76B3-496F-91C7-932E1F259529
ms.date: 02/15/2018
ms.keywords: GNSS_FIXSESSIONTYPE, GNSS_FIXSESSIONTYPE enumeration [Sensor Devices], GNSS_FixSession_ContinuousTracking, GNSS_FixSession_DistanceTracking, GNSS_FixSession_LKG, GNSS_FixSession_SingleShot, gnss.gnss_fixsessiontype, gnssdriver/GNSS_FIXSESSIONTYPE, gnssdriver/GNSS_FixSession_ContinuousTracking, gnssdriver/GNSS_FixSession_DistanceTracking, gnssdriver/GNSS_FixSession_LKG, gnssdriver/GNSS_FixSession_SingleShot
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_FIXSESSIONTYPE
product:
- Windows
targetos: Windows
req.typenames: GNSS_FIXSESSIONTYPE
---

# GNSS_FIXSESSIONTYPE enumeration


## -description


This enumeration indicates the type of location fix needed by the GNSS adapter when it issues an <a href="https://msdn.microsoft.com/library/windows/hardware/dn917750">IOCTL_GNSS_START_FIXSESSION</a> control code. This enumeration is set within the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925152">GNSS_FIXSESSION_PARAM</a> structure.


## -enum-fields




### -field GNSS_FixSession_SingleShot

The session request is a single-shot request. The GNSS driver will return intermediate fixes on request. Once a final fix is delivered, no further fix will be returned for this fix session and the GNSS adapter issues a stop fix.


### -field GNSS_FixSession_DistanceTracking

The start-fix request is for starting a tracking session such that a new fix is recorded and made available on request as soon as the device has moved beyond a specified threshold. No intermediate fix is required for a tracking session. A distance tracking session can be started even when another fix session of a different type is active. Both the fix sessions will continue getting the fixes as appropriate.


### -field GNSS_FixSession_ContinuousTracking

The start fix request is for starting a tracking session such that the device position is reported continuously.


### -field GNSS_FixSession_LKG

This session request is for a single-shot request, without starting any satellite acquisition/tracking activity by the underlying GNSS engine. The GNSS driver returns the cached copy (either from the engine or from the drivers own memory) of the last known position of the device, along with the timestamp. If no cached fix is available either in the engine or in the driver, an error is returned. No intermediate fix is returned for this session. Once the LKG fix or an error fix is returned the GNSS adapter issues a stop fix.

