---
UID: NC:dispmprt.DXGKCB_QUERY_SERVICES
title: DXGKCB_QUERY_SERVICES
author: windows-driver-content
description: The DxgkCbQueryServices function returns an interface implemented by the display port driver.
old-location: display\dxgkcbqueryservices.htm
old-project: display
ms.assetid: 0ce5df90-2019-4a92-97d6-0218acc8b1e8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKCB_QUERY_SERVICES, DpFunctions_1bf190e2-3bfc-4ea9-942a-502ec71fa362.xml, DxgkCbQueryServices, DxgkCbQueryServices callback function [Display Devices], display.dxgkcbqueryservices, dispmprt/DxgkCbQueryServices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	dispmprt.h
api_name:
-	DxgkCbQueryServices
product: Windows
targetos: Windows
req.typenames: SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
---

# DXGKCB_QUERY_SERVICES callback


## -description


The <b>DxgkCbQueryServices</b> function returns an interface implemented by the display port driver.


## -parameters




### -param DeviceHandle [in]

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560942">DXGKRNL_INTERFACE</a> structure that was passed to <a href="https://msdn.microsoft.com/ffacbb39-2581-4207-841d-28ce57fbc64d">DxgkDdiStartDevice</a>.


### -param ServicesType [in]

A constant from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562049">DXGK_SERVICES</a> enumeration that specifies which interface is being requested. This parameter must be set to <b>DxgkServicesAgp</b>, <b>DxgkServicesDebugReport</b>, or <b>DxgkServicesTimedOperation</b>, as those are the only supported interfaces.


### -param Interface [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure that receives the requested interface.


## -returns



<b>DxgkCbQueryServices</b> returns STATUS_SUCCESS if it succeeds. Otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.




## -remarks



An interface, in this context, is a set of functions implemented by the display port driver. The display port driver makes the functions of an interface available to other drivers by providing function pointers in response to <b>DxgkCbQueryServices</b>.

To obtain an AGP interface, do the following:

<ol>
<li>
Allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560949">DXGK_AGP_INTERFACE</a> structure.

</li>
<li>
Set the <b>Size</b> member to sizeof(DXGK_AGP_INTERFACE).

</li>
<li>
Set the <b>Version</b> member. Version constants are defined in <i>Dispmprt.h</i> (for example, DXGK_AGP_INTERFACE_VERSION_1).

</li>
<li>
Call <b>DxgkCbQueryServices</b>; set <i>ServicesType</i> to <b>DxgkServicesAgp</b>, and set <i>Interface</i> to the address (cast as PINTERFACE) of your DXGK_AGP_INTERFACE structure.

</li>
<li>
On return from <b>DxgkCbQueryServices</b>, your DXGK_AGP_INTERFACE structure will contain pointers to the interface functions: <a href="https://msdn.microsoft.com/abac76e0-eb8a-450a-a797-3733a8f71990">AgpAllocatePool</a> and the like.

</li>
</ol>
To obtain a Debug Report interface, do the following:

<ol>
<li>
Allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561040">DXGK_DEBUG_REPORT_INTERFACE</a> structure.

</li>
<li>
Set the <b>Size</b> member to sizeof(DXGK_DEBUG_REPORT_INTERFACE).

</li>
<li>
Set the <b>Version</b> member. Version constants are defined in <i>Dispmprt.h</i> (for example,  DXGK_DEBUG_REPORT_INTERFACE_VERSION_1).

</li>
<li>
Call <b>DxgkCbQueryServices</b>; set <i>ServicesType</i> to <b>DxgkServicesDebugReport</b>, and set <i>Interface</i> to the address (cast as PINTERFACE) of your DXGK_DEBUG_REPORT_INTERFACE structure.

</li>
<li>
On return from <b>DxgkCbQueryServices</b>, your DXGK_DEBUG_REPORT_INTERFACE structure will contain pointers to the interface functions: <a href="https://msdn.microsoft.com/library/windows/hardware/ff549088">DbgReportCreate</a> and the like.

</li>
</ol>
To obtain a Timed Operation interface, do the following:

<ol>
<li>
Allocate a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562065">DXGK_TIMED_OPERATION_INTERFACE</a> structure.

</li>
<li>
Set the <b>Size</b> member to sizeof(DXGK_TIMED_OPERATION_INTERFACE).

</li>
<li>
Set the <b>Version</b> member. Version constants are defined in <i>Dispmprt.h</i> (for example,  DXGK_TIMED_OPERATION_INTERFACE_VERSION_1).

</li>
<li>
Call <b>DxgkCbQueryServices</b>; set <i>ServicesType</i> to <b>DxgkServicesTimedOperation</b>, and set <i>Interface</i> to the address (cast as PINTERFACE) of your DXGK_TIMED_OPERATION_INTERFACE structure.

</li>
<li>
On return from <b>DxgkCbQueryServices</b>, your DXGK_TIMED_OPERATION_INTERFACE structure will contain pointers to the interface functions: <a href="https://msdn.microsoft.com/library/windows/hardware/ff570084">TimedOperationStart</a> and the like.

</li>
</ol>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538228">AGP Interface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551798">Debug Report Interface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation Interface</a>
 

 

