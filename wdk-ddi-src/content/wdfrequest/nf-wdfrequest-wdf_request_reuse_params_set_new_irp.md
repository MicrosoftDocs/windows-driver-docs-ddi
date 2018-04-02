---
UID: NF:wdfrequest.WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
title: WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function
author: windows-driver-content
description: The WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function sets a new IRP in a driver's WDF_REQUEST_REUSE_PARAMS structure.
old-location: wdf\wdf_request_reuse_params_set_new_irp.htm
old-project: wdf
ms.assetid: 3a18ec1b-be02-418a-8a38-deca7178ce30
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_1c9cbd6c-35a3-4de2-84f9-9d9788002d31.xml, WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP, WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function, kmdf.wdf_request_reuse_params_set_new_irp, wdf.wdf_request_reuse_params_set_new_irp, wdfrequest/WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfrequest.h
api_name:
-	WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP
product:
- Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> function sets a new IRP in a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.


## -parameters




### -param Params [in, out]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure.


### -param NewIrp [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure.


## -returns



None




## -remarks



If a driver's call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a> specifies a new IRP structure, the driver must first call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552483">WDF_REQUEST_REUSE_PARAMS_INIT</a> and then call <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> to initialize a WDF_REQUEST_REUSE_PARAMS structure.

The <b>WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP</b> function sets the structure's <b>NewIrp</b> member to the specified IRP pointer. It also sets the <b>WDF_REQUEST_REUSE_SET_NEW_IRP</b> flag in the structure's <b>Flag</b> member.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a> structure, provides a new IRP structure for the I/O request, and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_REQUEST_REUSE_PARAMS  params;
NTSTATUS  status;
PIRP  myIrp;
...
WDF_REQUEST_REUSE_PARAMS_INIT(
                              &amp;params,
                              WDF_REQUEST_REUSE_NO_FLAGS,
                              STATUS_SUCCESS
                              );
WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP(
                                     &amp;params,
                                     myIrp
                                     );
status = WdfRequestReuse(
                         Request,
                         &amp;params
                         );
...</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552480">WDF_REQUEST_REUSE_PARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552483">WDF_REQUEST_REUSE_PARAMS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>
 

 

