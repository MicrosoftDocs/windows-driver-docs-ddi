---
UID: NE:pointofservicedriverinterface._MsrStatusUpdateType
title: "_MsrStatusUpdateType"
author: windows-driver-content
description: This enumeration defines the constants that indicate the magnetic stripe reader (MSR) status.
old-location: pos\msrstatusupdatetype.htm
old-project: pos
ms.assetid: f7e055ac-df7c-4993-b7aa-f455c4548d5e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: MsrStatusUpdateType, MsrStatusUpdateType enumeration, MsrStatusUpdateType_Authenticated, MsrStatusUpdateType_Extended, MsrStatusUpdateType_Off, MsrStatusUpdateType_OffOrOffline, MsrStatusUpdateType_Offline, MsrStatusUpdateType_Online, MsrStatusUpdateType_Unauthenticated, _MsrStatusUpdateType, pointofservicedriverinterface/MsrStatusUpdateType, pointofservicedriverinterface/MsrStatusUpdateType_Authenticated, pointofservicedriverinterface/MsrStatusUpdateType_Extended, pointofservicedriverinterface/MsrStatusUpdateType_Off, pointofservicedriverinterface/MsrStatusUpdateType_OffOrOffline, pointofservicedriverinterface/MsrStatusUpdateType_Offline, pointofservicedriverinterface/MsrStatusUpdateType_Online, pointofservicedriverinterface/MsrStatusUpdateType_Unauthenticated, pos.msrstatusupdatetype
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
-	pointofservicedriverinterface.h
api_name:
-	MsrStatusUpdateType
product: Windows
targetos: Windows
req.typenames: MsrStatusUpdateType
---

# _MsrStatusUpdateType enumeration


## -description


This enumeration defines the constants that indicate the magnetic stripe reader (MSR) status.


## -enum-fields




### -field MsrStatusUpdateType_Online

The device is powered on. This is valid if <a href="https://msdn.microsoft.com/e0263969-1c6a-4805-a647-d4b9df83ef71">UnifiedPosPowerReportingType</a> is <b>Standard</b> or <b>Advanced</b>.


### -field MsrStatusUpdateType_Off

The device is powered off or is detached from the terminal. This is valid if <a href="https://msdn.microsoft.com/e0263969-1c6a-4805-a647-d4b9df83ef71">UnifiedPosPowerReportingType</a> is <b>Advanced</b>.


### -field MsrStatusUpdateType_Offline

The device is powered on but is not ready, or is unable, to respond to requests. This is valid if <a href="https://msdn.microsoft.com/e0263969-1c6a-4805-a647-d4b9df83ef71">UnifiedPosPowerReportingType</a> is <b>Advanced</b>.


### -field MsrStatusUpdateType_OffOrOffline

The device is either off or offline. This is valid if <a href="https://msdn.microsoft.com/e0263969-1c6a-4805-a647-d4b9df83ef71">UnifiedPosPowerReportingType</a> is <b>Standard</b>.


### -field MsrStatusUpdateType_Unauthenticated

The device is not authenticated. This is valid if the device supports authentication.


### -field MsrStatusUpdateType_Authenticated

The device is authenticated. This is valid if the device supports authentication.


### -field MsrStatusUpdateType_Extended

Vendor-specific status information. Reported in IMagneticStripeReaderStatusUpdatedEventArgs.ExtendedStatus.

