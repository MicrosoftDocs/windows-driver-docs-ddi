---
UID: NF:wdfrequest.WdfRequestWdmGetIrp
title: WdfRequestWdmGetIrp function
author: windows-driver-content
description: The WdfRequestWdmGetIrp method returns the WDM IRP structure that is associated with a specified framework request object.
old-location: wdf\wdfrequestwdmgetirp.htm
old-project: wdf
ms.assetid: 414950c6-b082-4ea9-bba4-f3d12b4d2a9e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRequestObjectRef_2f8bba17-817e-4edb-98f2-bd56eb3e34ac.xml, WdfRequestWdmGetIrp, WdfRequestWdmGetIrp method, kmdf.wdfrequestwdmgetirp, wdf.wdfrequestwdmgetirp, wdfrequest/WdfRequestWdmGetIrp
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
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
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
-	WdfRequestWdmGetIrp
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestWdmGetIrp function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfRequestWdmGetIrp</b> method returns the WDM <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure that is associated with a specified framework request object.


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns



<b>WdfRequestWdmGetIrp</b> returns a pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The driver must not access a request's IRP structure after <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-i-o-requests">completing the I/O request</a>.

For more information about <b>WdfRequestWdmGetIrp</b>, see <a href="https://msdn.microsoft.com/a686ea00-6987-480a-a4ce-892e1efbed87">Obtaining Information About an I/O Request</a>.


#### Examples

The following code example is part of an <a href="https://msdn.microsoft.com/3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce">EvtIoDeviceControl</a> callback function that obtains the WDM IRP that is associated with an I/O request and then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549266">IoGetNextIrpStackLocation</a> to obtain the next-lower driver's I/O stack location.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
MyEvtIoDeviceControl(
    IN WDFQUEUE  Queue,
    IN WDFREQUEST  Request,
    IN size_t  OutputBufferLength,
    IN size_t  InputBufferLength,
    IN ULONG  IoControlCode
    )
{
    PIRP  irp = NULL;
    PIO_STACK_LOCATION  nextStack;
...
    irp = WdfRequestWdmGetIrp(Request);
    nextStack = IoGetNextIrpStackLocation(irp);
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>
 

 

