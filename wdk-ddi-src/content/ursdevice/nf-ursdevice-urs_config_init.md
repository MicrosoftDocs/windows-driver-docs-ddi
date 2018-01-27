---
UID: NF:ursdevice.URS_CONFIG_INIT
title: URS_CONFIG_INIT function
author: windows-driver-content
description: Initializes a URS_CONFIG structure.
old-location: buses\urs_config_init.htm
old-project: usbref
ms.assetid: 72229643-1177-4884-94A9-89920A5488A6
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.urs_config_init, ursdevice/URS_CONFIG_INIT, URS_CONFIG_INIT, URS_CONFIG_INIT function [Buses]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ursdevice.h
apiname: 
-	URS_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: UMDETW_ALLOCATION_USAGE
req.product: Windows 10 or later.
---

# URS_CONFIG_INIT function


## -description


Initializes a <a href="..\ursdevice\ns-ursdevice-_urs_config.md">URS_CONFIG</a> structure. 


## -syntax


````
FORCEINLINE void URS_CONFIG_INIT(
  _Out_ PURS_CONFIG                                 Config,
  _In_  URS_HOST_INTERFACE_TYPE                     HostInterfaceType,
  _In_  PFN_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS EvtUrsFilterRemoveResourceRequirements
);
````


## -parameters




### -param Config [out]

 A pointer to a <a href="..\ursdevice\ns-ursdevice-_urs_config.md">URS_CONFIG</a> structure to initialize.


### -param HostInterfaceType [in]

 A <a href="..\urstypes\ne-urstypes-_urs_host_interface_type.md">URS_HOST_INTERFACE_TYPE</a> type value that indicates the type of host controller that the dual-role controller implements.


### -param EvtUrsFilterRemoveResourceRequirements [in]

 A  pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt595921">EVT_URS_DEVICE_FILTER_RESOURCE_REQUIREMENTS</a> callback function that is implemented by the  client driver.


## -returns


This function does not return a value.



## -see-also

<a href="..\ursdevice\ns-ursdevice-_urs_config.md">URS_CONFIG</a>

<a href="..\ursdevice\nf-ursdevice-ursdeviceinitialize.md">UrsDeviceInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20URS_CONFIG_INIT function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

