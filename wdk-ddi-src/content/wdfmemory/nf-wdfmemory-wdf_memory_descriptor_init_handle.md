---
UID: NF:wdfmemory.WDF_MEMORY_DESCRIPTOR_INIT_HANDLE
title: WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function
author: windows-driver-content
description: The WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function initializes a WDF_MEMORY_DESCRIPTOR structure so that it describes a specified framework memory object.
old-location: wdf\wdf_memory_descriptor_init_handle.htm
tech.root: wdf
ms.assetid: e5449684-dd37-4d49-ae9f-372f295cecf8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFMemoryObjectRef_1cec1e9e-7279-4278-a5c2-2eaaaa7a8074.xml, WDF_MEMORY_DESCRIPTOR_INIT_HANDLE, WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function, kmdf.wdf_memory_descriptor_init_handle, wdf.wdf_memory_descriptor_init_handle, wdfmemory/WDF_MEMORY_DESCRIPTOR_INIT_HANDLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA
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
-	wdfmemory.h
api_name:
-	WDF_MEMORY_DESCRIPTOR_INIT_HANDLE
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_MEMORY_DESCRIPTOR_INIT_HANDLE function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a> structure so that it describes a specified framework memory object.


## -parameters




### -param Descriptor [out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a> structure.


### -param Memory [in]

A handle to a framework memory object.


### -param Offsets [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure. This parameter is optional and can be <b>NULL</b>.


## -returns



None




## -remarks



The <b>WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a> structure and sets the structure's <b>Type</b> member to <b>WdfMemoryDescriptorTypeHandle</b>. Then it sets the structure's <b>u.HandleType.Memory</b> and <b>u.HandleType.Offsets</b> members to the values that the <i>Memory</i> and <i>Offsets</i> parameters specify, respectively.


#### Examples

The following code example obtains a handle to a framework memory object that represents an I/O request's input buffer. The example uses the memory object handle to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a> structure. Then, the example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552568">WDF_USB_CONTROL_SETUP_PACKET</a> structure and sends a USB control transfer request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFMEMORY  memory;
WDF_MEMORY_DESCRIPTOR  memDesc;
WDF_USB_CONTROL_SETUP_PACKET  controlSetupPacket;
NTSTATUS  status;

status = WdfRequestRetrieveInputMemory(
                                       Request,
                                       &amp;memory
                                       );
if (!NT_SUCCESS(status)) {
    break;
}
WDF_MEMORY_DESCRIPTOR_INIT_HANDLE(
                                  &amp;memDesc,
                                  memory,
                                  NULL
                                  );

WDF_USB_CONTROL_SETUP_PACKET_INIT_VENDOR(
                                         &amp;controlSetupPacket,
                                         BmRequestHostToDevice,
                                         BmRequestToDevice,
                                         USBFX2LK_SET_BARGRAPH_DISPLAY,
                                         0,
                                         0
                                         );

status = WdfUsbTargetDeviceSendControlTransferSynchronously(
                                  pDevContext-&gt;UsbDevice,
                                  NULL,
                                  NULL,
                                  &amp;controlSetupPacket,
                                  &amp;memDesc,
                                  (PULONG)&amp;bytesTransferred
                                  );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552392">WDF_MEMORY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552393">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552396">WDF_MEMORY_DESCRIPTOR_INIT_MDL</a>
 

 

