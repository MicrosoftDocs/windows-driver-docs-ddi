---
UID: NF:ufxclient.UfxFdoInit
title: UfxFdoInit function
author: windows-driver-content
description: Initializes the WDFDEVICE_INIT structure that the client driver subsequently provides when it calls WdfDeviceCreate.
old-location: buses\ufxfdoinit.htm
tech.root: usbref
ms.assetid: 11CDA6DA-6B26-41BC-8F0B-2F18FC03B3C2
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: UfxFdoInit, UfxFdoInit method [Buses], buses.ufxfdoinit, ufxclient/UfxFdoInit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxFdoInit
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxFdoInit function


## -description


Initializes the WDFDEVICE_INIT structure that the client driver subsequently provides when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.


## -parameters




### -param WdfDriver [in]

A handle to the driver's WDF driver object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547336">WdfGetDriver</a>.


### -param DeviceInit [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param FdoAttributes [in, out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that describes object attributes for the 


## -returns



If the operation is successful, the method returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE.




## -remarks



The client driver receives a pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.  It then calls <b>UfxFdoInit</b> with this pointer before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> to create the WDFDEVICE object.

By default, for WDF drivers, the device's function driver is the power policy owner.

The following code snippet shows how to call <b>UfxFdoInit</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
UfxClientDeviceCreate(
    _In_ WDFDRIVER Driver,
    _In_ PWDFDEVICE_INIT DeviceInit
    )
/*++

Routine Description:

    Worker routine called to create a device and its software resources.

Arguments:

    Driver - WDF driver object

    DeviceInit - Pointer to an opaque init structure. Memory for this
                 structure will be freed by the framework when WdfDeviceCreate
                 succeeds. So don't access the structure after that point.

Return Value:

    Appropriate NTSTATUS value

--*/
{
    WDF_OBJECT_ATTRIBUTES DeviceAttributes;
    WDFDEVICE WdfDevice;

    PAGED_CODE();

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;DeviceAttributes, CONTROLLER_CONTEXT);

    //
    // Do UFX-specific initialization
    //
    Status = UfxFdoInit(Driver, DeviceInit, &amp;DeviceAttributes);

    //
    // Proceed to WdfDeviceCreate
    //
    
    ...

}</pre>
</td>
</tr>
</table></span></div>


