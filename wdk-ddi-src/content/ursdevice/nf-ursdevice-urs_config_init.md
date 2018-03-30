---
UID: NF:ursdevice.URS_CONFIG_INIT
title: URS_CONFIG_INIT function
author: windows-driver-content
description: Initializes a URS_CONFIG structure.
old-location: buses\urs_config_init.htm
old-project: usbref
ms.assetid: 72229643-1177-4884-94A9-89920A5488A6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: URS_CONFIG_INIT, URS_CONFIG_INIT function [Buses], buses.urs_config_init, ursdevice/URS_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ursdevice.h
req.include-header: Urscx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
-	Ursdevice.h
api_name:
-	URS_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# URS_CONFIG_INIT function


## -description


Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628020">URS_CONFIG</a> structure. 


## -parameters




### -param Config [out]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt628020">URS_CONFIG</a> structure to initialize.


### -param HostInterfaceType [in]

 A <a href="https://msdn.microsoft.com/library/windows/hardware/mt628023">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of host controller that the dual-role controller implements.


### -param EvtUrsFilterRemoveResourceRequirements [in]

 A  pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function that is implemented by the  client driver.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt628020">URS_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt628012">UrsDeviceInitialize</a>
 

 

