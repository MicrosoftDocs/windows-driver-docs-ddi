---
UID: NF:wdfrequest.WdfRequestCreateFromIrp
title: WdfRequestCreateFromIrp function
author: windows-driver-content
description: The WdfRequestCreateFromIrp method creates a framework request object from a specified WDM IRP.
old-location: wdf\wdfrequestcreatefromirp.htm
old-project: wdf
ms.assetid: 7fc67320-6943-4e39-8474-28c24265eae2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_fb959453-1aab-4e2d-8877-356ce04b5784.xml, WdfRequestCreateFromIrp, WdfRequestCreateFromIrp method, kmdf.wdfrequestcreatefromirp, wdf.wdfrequestcreatefromirp, wdfrequest/WdfRequestCreateFromIrp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfRequestCreateFromIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRequestCreateFromIrp function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestCreateFromIrp</b> method creates a framework request object from a specified WDM IRP.


## -parameters




### -param RequestAttributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the request object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES. 


### -param Irp [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure that contains a WDM I/O request packet.


### -param RequestFreesIrp [in]

A Boolean value that, if <b>TRUE</b>, indicates that the framework removes the IRP when the request handle is destroyed. If <b>FALSE</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a> to remove the IRP, using the steps that the following Examples section demonstrates.


### -param Request [out]

A pointer to a location that receives a handle to a framework request object. 


## -returns



<b>WdfRequestCreateFromIrp</b>  returns STATUS_SUCCESS if the operation succeeds. For a list of additional return values, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.







## -remarks



Typically, framework-based drivers call <b>WdfRequestCreateFromIrp</b> only if they receive WDM IRPs in a WDM dispatch routine and then forward the requests to framework I/O targets.

If a driver calls <b>WdfRequestCreateFromIrp</b> to create a request object, it must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> for the request object. Instead, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a> when it has finished using the request object.

In addition, the driver must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550019">WdfRequestRetrieveOutputMemory</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550018">WdfRequestRetrieveOutputBuffer</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff550014">WdfRequestRetrieveInputBuffer</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550015">WdfRequestRetrieveInputMemory</a> with the new request object.

By default, the new request object's parent is the framework driver object that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a> method created. You can use the <b>ParentObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure to specify a different parent. The framework deletes the request object when it deletes the parent object. If your driver does not change the default parent, the driver should delete the request object when it has finished using the object; otherwise, the request object will remain until the I/O manager unloads your driver. 

For more information about creating framework request objects, see <a href="https://msdn.microsoft.com/4bd668ec-14fb-4999-9535-a49712a26ba6">Creating Framework Request Objects</a>.

Framework-based drivers must not use the <b>Tail.Overlay.DriverContext</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure, because the framework uses this member.


#### Examples

<b>Example 1</b>

The following code example creates a framework request object from a specified WDM IRP and then deletes it. This example sets the <i>RequestFreesIrp</i> parameter to <b>TRUE</b>, so the framework removes the IRP when the request handle is destroyed.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFREQUEST request;
PIRP irp;

//Creation
status = WdfRequestCreateFromIrp(
                                 WDF_NO_OBJECT_ATTRIBUTES,
                                 irp,
                                 TRUE,
                                 &amp;request
                                 );
...
//Deletion
WdfObjectDelete(request);</pre>
</td>
</tr>
</table></span></div>
<b>Example 2</b>

The following code example also creates a framework request object from a specified WDM IRP and then deletes it. This example sets the <i>RequestFreesIrp</i> parameter to <b>FALSE</b>, so the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a> to remove the IRP. All of the function calls in the example  are required.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_REQUEST_REUSE_PARAMS params;
WDFREQUEST request;
PIRP irp;

//Creation
status = WdfRequestCreateFromIrp(
                                 WDF_NO_OBJECT_ATTRIBUTES,
                                 irp,
                                 FALSE,
                                 &amp;request
                                 );
...
//Deletion
WDF_REQUEST_REUSE_PARAMS_INIT(
                              &amp;params,
                              WDF_REQUEST_REUSE_NO_FLAGS,
                              STATUS_SUCCESS
                              );
WDF_REQUEST_REUSE_PARAMS_SET_NEW_IRP(
                                     &amp;params,
                                     NULL
                                     );
status = WdfRequestReuse(
                         request,
                         &amp;params
                         );
ASSERT(NT_SUCCESS(status));
IoFreeIrp(irp);
WdfObjectDelete(request);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh454223">IoFreeIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546786">WdfDeviceInitSetRequestAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549951">WdfRequestCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550026">WdfRequestReuse</a>
 

 

