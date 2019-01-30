---
UID: NF:wdfrequest.WDF_REQUEST_FORWARD_OPTIONS_INIT
title: WDF_REQUEST_FORWARD_OPTIONS_INIT function (wdfrequest.h)
description: The WDF_REQUEST_FORWARD_OPTIONS_INIT function initializes a WDF_REQUEST_FORWARD_OPTIONS structure.
old-location: wdf\wdf_request_forward_options_init.htm
tech.root: wdf
ms.assetid: 301b4b63-0337-4f78-a4f8-6b2d2b168663
ms.date: 02/26/2018
ms.keywords: DFRequestObjectRef_ade75e55-accb-4fe0-a1be-b5acd9e4c34b.xml, WDF_REQUEST_FORWARD_OPTIONS_INIT, WDF_REQUEST_FORWARD_OPTIONS_INIT function, kmdf.wdf_request_forward_options_init, wdf.wdf_request_forward_options_init, wdfrequest/WDF_REQUEST_FORWARD_OPTIONS_INIT
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
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
-	wdfrequest.h
api_name:
-	WDF_REQUEST_FORWARD_OPTIONS_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_REQUEST_FORWARD_OPTIONS_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552459">WDF_REQUEST_FORWARD_OPTIONS</a> structure.


## -parameters




### -param ForwardOptions [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552459">WDF_REQUEST_FORWARD_OPTIONS</a> structure.


## -returns



None.




## -remarks



Before a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>, it must call <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b> to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552459">WDF_REQUEST_FORWARD_OPTIONS</a> structure.

The <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552459">WDF_REQUEST_FORWARD_OPTIONS</a> structure and sets the structure's <b>Size</b> member. Then the function sets the <a href="https://msdn.microsoft.com/6161bfd3-482c-4571-bd88-2e25d32b34a0">WDF_REQUEST_FORWARD_OPTION_SEND_AND_FORGET</a> flag.

For a code example that uses <b>WDF_REQUEST_FORWARD_OPTIONS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552459">WDF_REQUEST_FORWARD_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549959">WdfRequestForwardToParentDeviceIoQueue</a>
 

 

