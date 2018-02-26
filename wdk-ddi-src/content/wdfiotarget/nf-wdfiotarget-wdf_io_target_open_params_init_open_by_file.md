---
UID: NF:wdfiotarget.WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE
title: WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function initializes a driver's WDF_IO_TARGET_OPEN_PARAMS structure so the driver can open an I/O target by specifying a filename.
old-location: wdf\wdf_io_target_open_params_init_open_by_file.htm
old-project: wdf
ms.assetid: 6C8CA2A8-D39E-4524-A909-102D8310AC72
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , A, B, D, E, F, G, I, L, M, N, O, P, R, S, T, W, WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE, WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function, Y, _, wdf.wdf_io_target_open_params_init_open_by_file, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
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
-	WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</b> function initializes a driver's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure so the driver can open an I/O target by specifying a filename.


## -syntax


````
void WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE(
  _Out_    PWDF_IO_TARGET_OPEN_PARAMS Params,
  _In_opt_ PCUNICODE_STRING           FileName
);
````


## -parameters




### -param Params [out]

A pointer to a driver-allocated <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure, which the function initializes.


### -param FileName [in, optional]

A value for the <b>FileName</b> member of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure. Most drivers specify <b>NULL</b> here unless the lower target supports <a href="https://msdn.microsoft.com/e5312297-849f-4b4e-835d-0ce5295c7ce2">Device Namespace Access</a>.


## -returns



This function does not return a value.




## -remarks



The <b>WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</b> function zeros the specified <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure and sets its <b>Size</b> member. It also sets the structure's <b>Type</b> member to <b>WdfIoTargetOpenLocalTargetByFile</b> and sets the <b>FileName</b> member if the driver supplies a filename.

A driver can explicitly close the I/O target by calling <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a>. If the driver does not explicitly close the target, the framework closes the target automatically when the device is removed (an I/O target is by default parented to the device).


#### Examples

The following code example shows how a UMDF driver can open a local target with a file object as described in <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WDF_IO_TARGET_OPEN_TYPE</a>:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  ioTargetAttrib;
WDFIOTARGET  ioTarget;
WDF_IO_TARGET_OPEN_PARAMS  openParams;

//
// Create target
//
WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;ioTargetAttrib, TARGET_DEVICE_INFO);
status = WdfIoTargetCreate(device, &amp;ioTargetAttrib, &amp;ioTarget);
if (!NT_SUCCESS(status)) {
    return status;
}

//
// Open target
//
WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE(&amp;openParams, NULL);
status = WdfIoTargetOpen(ioTarget, &amp;openParams);
if (!NT_SUCCESS(status)) {
    WdfObjectDelete(ioTarget);
    return status;
}

//
// create a request
//


//
// Format the request for the above target
//


//
// Send request to above target
//
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WDF_IO_TARGET_OPEN_TYPE</a>



<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

