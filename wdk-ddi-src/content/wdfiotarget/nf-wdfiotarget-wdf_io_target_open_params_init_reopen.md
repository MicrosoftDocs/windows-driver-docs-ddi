---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can reopen a remote I/O target.
old-location: wdf\wdf_io_target_open_params_init_reopen.htm
old-project: wdf
ms.assetid: 00f1e870-4c74-44d3-9ee9-c8b9e63e5f3b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN, DFIOTargetRef_f0c123bb-3ecc-401f-ad91-4ed1b359454d.xml, WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function, wdf.wdf_io_target_open_params_init_reopen, kmdf.wdf_io_target_open_params_init_reopen, WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfiotarget.h
apiname:
-	WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function initializes a driver's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can reopen a remote I/O target. 


## -syntax


````
VOID WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN(
  _Out_ PWDF_IO_TARGET_OPEN_PARAMS Params
);
````


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.


## -returns



None




## -remarks



The <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure is used as input to the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> method. Your driver should call <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> to initialize a <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure if the driver is calling <b>WdfIoTargetOpen</b> from within an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a> callback function.

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</b> function zeros the specified <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure and sets the structure's <b>Size</b> member. Then, the function sets the <b>Type</b> member to <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WdfIoTargetOpenReopen</a>.

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example is a segment of an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a> callback function that reopens a remote I/O target.

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

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>



<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a>



<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>



<a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WdfIoTargetOpenReopen</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

