---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can reopen a remote I/O target.
old-location: wdf\wdf_io_target_open_params_init_reopen.htm
old-project: wdf
ms.assetid: 00f1e870-4c74-44d3-9ee9-c8b9e63e5f3b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_f0c123bb-3ecc-401f-ad91-4ed1b359454d.xml, WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN, WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function, kmdf.wdf_io_target_open_params_init_reopen, wdf.wdf_io_target_open_params_init_reopen, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfiotarget.h
api_name:
-	WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can reopen a remote I/O target. 


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.


## -returns



None




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a> method. Your driver should call <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> to initialize a <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure if the driver is calling <b>WdfIoTargetOpen</b> from within an <a href="https://msdn.microsoft.com/9f275a2c-6f40-461d-bd2c-767b2494ad1c">EvtIoTargetRemoveCanceled</a> callback function.

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a> structure and sets the structure's <b>Size</b> member. Then, the function sets the <b>Type</b> member to <a href="https://msdn.microsoft.com/27aa5d78-03ce-4fc9-b1c8-d02a760e2787">WdfIoTargetOpenReopen</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example is a segment of an <a href="https://msdn.microsoft.com/9f275a2c-6f40-461d-bd2c-767b2494ad1c">EvtIoTargetRemoveCanceled</a> callback function that reopens a remote I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoTargetRemoveCanceled(
    WDFIOTARGET IoTarget
    )
{
    WDF_IO_TARGET_OPEN_PARAMS openParams;
    NTSTATUS status;

...
    WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN(&amp;openParams);
    status = WdfIoTargetOpen(
                             IoTarget,
                             &amp;openParams
                             );
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/9f275a2c-6f40-461d-bd2c-767b2494ad1c">EvtIoTargetRemoveCanceled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552377">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548634">WdfIoTargetOpen</a>



<a href="https://msdn.microsoft.com/27aa5d78-03ce-4fc9-b1c8-d02a760e2787">WdfIoTargetOpenReopen</a>
 

 

