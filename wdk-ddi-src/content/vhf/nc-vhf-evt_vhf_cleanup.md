---
UID: NC:vhf.EVT_VHF_CLEANUP
title: EVT_VHF_CLEANUP
author: windows-driver-content
description: The HID source driver implements this event callback to free resources that might the driver allocated to the virtual HID device.
old-location: hid\evtvhfcleanup.htm
tech.root: hid
ms.assetid: 1D477E7B-E4EA-46E7-872C-3BEBFBD31702
ms.date: 4/30/2018
ms.keywords: EVT_VHF_CLEANUP, EVT_VHF_CLEANUP callback, EvtVhfCleanup, EvtVhfCleanup callback function [Human Input Devices], hid.evtvhfcleanup, vhf/EvtVhfCleanup
ms.topic: callback
req.header: vhf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: None supported
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	vhf.h
api_name:
-	EvtVhfCleanup
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_VHF_CLEANUP callback function


## -description


The HID source driver implements this event callback to free resources that might the driver allocated to the virtual HID device. 


## -parameters




### -param VhfClientContext [in]

Pointer to the HID source driver-defined context structure that the driver passed in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/dn925036">VhfCreate</a> to create the virtual HID device.


## -returns



This callback function does not return a value.




## -remarks



To delete the virtual HID device, the HID source driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/dn925038">VhfDelete</a>. That call causes Virtual HID Framework (VHF) to invoke the previously-registered <i>EvtVhfCleanup</i>, if the callback function is  implemented by the HID source driver.  When the driver calls VhfDelete with <i>Wait</i> set to TRUE, <i>EvtVhfCleanup</i> gets called before <b>VhfDelete</b> returns. If <i>Wait</i> is FALSE, it might get called any time after <b>VhfDelete</b> is called that is before or after <b>VhfDelete</b> returns.

The call gives the HID source driver an opportunity to free resources allocated for the virtual HID device when that device is deleted. 

The HID source driver must not use the VHFHANDLE for the virtual HID device (created by <a href="https://msdn.microsoft.com/library/windows/hardware/dn925036">VhfCreate</a>) after this callback function returns. Before invoking this callback function, VHF makes sure that there are no asynchronous operations pending.




## -see-also




<a href="https://msdn.microsoft.com/26964963-792F-4529-B4FC-110BF5C65B35">Write a HID source driver by using Virtual HID Framework (VHF)</a>
 

 

