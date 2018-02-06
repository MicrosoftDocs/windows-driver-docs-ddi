---
UID: NS:pointofservicedriverinterface._MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA
title: "_MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA"
author: windows-driver-content
description: This structure contains authentication information retrieved from the device.
old-location: pos\msr_retrieve_device_authentication_data.htm
old-project: pos
ms.assetid: e355ca5b-d396-4748-a0ec-b12294a6dcfa
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: pos.msr_retrieve_device_authentication_data, pointofservicedriverinterface/MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA, MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA, MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA structure, PMSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA, *PMSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA, PMSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA structure pointer, pointofservicedriverinterface/PMSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA, _MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
-	PointOfServiceDriverInterface.h
apiname:
-	MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA
product: Windows
targetos: Windows
req.typenames: MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA, *PMSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA
---

# _MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA structure


## -description


This structure contains authentication information retrieved from the device.


## -syntax


````
typedef struct _MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA {
  unsigned char KeySerialNumber[MSR_KEY_SERIAL_NUMBER_SIZE];
  unsigned char Challenge1[MSR_CHALLENGE_SIZE];
  unsigned char Challenge2[MSR_CHALLENGE_SIZE];
} MSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA, *PMSR_RETRIEVE_DEVICE_AUTHENTICATION_DATA;
````


## -struct-fields




### -field KeySerialNumber

Unused.


### -field Challenge1

Authentication challenge, such as a password.


### -field Challenge2

Deauthentication challenge, such as a password.

