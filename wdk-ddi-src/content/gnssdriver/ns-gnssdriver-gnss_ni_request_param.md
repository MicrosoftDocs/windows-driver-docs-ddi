---
UID: NS:gnssdriver.GNSS_NI_REQUEST_PARAM
title: GNSS_NI_REQUEST_PARAM
author: windows-driver-content
description: This structure contains the NI request parameters.
old-location: gnss\gnss_ni_request_param.htm
tech.root: gnss
ms.assetid: 0528EEE6-31D6-4CF6-8192-3557C28B4D10
ms.date: 2/15/2018
ms.keywords: "*PGNSS_NI_REQUEST_PARAM, GNSS_NI_REQUEST_PARAM, GNSS_NI_REQUEST_PARAM structure [Sensor Devices], PGNSS_NI_REQUEST_PARAM, PGNSS_NI_REQUEST_PARAM structure pointer [Sensor Devices], gnss.gnss_ni_request_param, gnssdriver/GNSS_NI_REQUEST_PARAM, gnssdriver/PGNSS_NI_REQUEST_PARAM"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_NI_REQUEST_PARAM
product:
- Windows
targetos: Windows
req.typenames: GNSS_NI_REQUEST_PARAM, *PGNSS_NI_REQUEST_PARAM
---

# GNSS_NI_REQUEST_PARAM structure


## -description


This structure contains the NI request parameters.


## -struct-fields




### -field Size

Structure size.


### -field Version

Version number.


### -field RequestId

The ID that uniquely identifies the NI request. It is used later by the NI response to identify the request to respond to.


### -field RequestType

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn925194">GNSS_NI_REQUEST_TYPE</a> enumeration value that specifies the request type.


### -field NotificationType

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn925185">GNSS_NI_NOTIFICATION_TYPE</a> enumeration value that specifies the notification type.


### -field RequestPlaneType

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn925188">GNSS_NI_PLANE_TYPE</a> enumeration value that specifies the plane type.


### -field SuplNiInfo

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn925231">GNSS_SUPL_NI_INFO</a> structure that contains the SUPL NI information.


### -field CpNiInfo

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn925101">GNSS_CP_NI_INFO</a> structure that contains CP NI information.


### -field V2UplNiInfo

V2Upl NI request information.


### -field ResponseTimeInSec

The required response time, in seconds.


### -field EmergencyLocation

Indicates an emergency request, so an existing NI dialog will be dismissed and the new request will be processed immediately.

