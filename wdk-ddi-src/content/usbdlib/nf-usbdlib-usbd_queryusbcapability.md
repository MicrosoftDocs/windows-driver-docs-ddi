---
UID: NF:usbdlib.USBD_QueryUsbCapability
title: USBD_QueryUsbCapability function
author: windows-driver-content
description: The USBD_QueryUsbCapability routine is called by a WDM client driver to determine whether the underlying USB driver stack and the host controller hardware support a specific capability.
old-location: buses\usbd_getcapability.htm
old-project: usbref
ms.assetid: 982B52A2-5BC1-4390-AE44-C3D31E2FC3DB
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , B, C, D, Q, S, U, USBD_QueryUsbCapability, USBD_QueryUsbCapability routine [Buses], _, a, b, buses.usbd_getcapability, e, i, l, p, r, s, t, u, usbdlib/USBD_QueryUsbCapability, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbdex.lib
-	Usbdex.dll
apiname:
-	USBD_QueryUsbCapability
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_QueryUsbCapability function


## -description


The <b>USBD_QueryUsbCapability</b> routine is called by a WDM client driver to determine whether the underlying USB driver stack and the host controller hardware support a specific capability. <b>Note for Windows Driver Framework (WDF) Drivers:  </b>If your client driver is a WDF-based driver, then you must call the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicequeryusbcapability.md">WdfUsbTargetDeviceQueryUsbCapability</a> method instead of <b>USBD_QueryUsbCapability</b>.




## -syntax


````
NTSTATUS USBD_QueryUsbCapability(
  _In_      USBD_HANDLE USBDHandle,
  _In_      PGUID       CapabilityType,
  _In_      ULONG       OutputBufferLength,
  _Inout_   PUCHAR      OutputBuffer,
  _Out_opt_ PULONG      ResultLength
);
````


## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a> routine.


### -param CapabilityType [in]

Pointer to a GUID that represents the capability for which the client driver wants to retrieve information. The possible  <i>PGUID</i>  values are  as follows:

<ul>
<li>GUID_USB_CAPABILITY_CHAINED_MDLS</li>
<li>GUID_USB_CAPABILITY_STATIC_STREAMS</li>
<li>GUID_USB_CAPABILITY_SELECTIVE_SUSPEND</li>
<li>GUID_USB_CAPABILITY_FUNCTION_SUSPEND

</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE</li>
<li>GUID_USB_CAPABILITY_TIME_SYNC</li>
</ul>

### -param OutputBufferLength [in]

Length, in bytes, of the buffer pointed to by <i>OutputBuffer</i>.


### -param OutputBuffer [in, out]

Pointer to a caller-allocated buffer. Certain capability requests return additional information in an output buffer. For those requests, you must allocate the buffer and provide a pointer to the buffer in the <i>OutputBuffer</i> parameter. Currently, only the static-streams capability request requires an output buffer of the type USHORT. The buffer is filled by <b>USBD_QueryUsbCapability</b> with the maximum number of streams supported per endpoint.

Other capability requests do not require an output buffer. For those requests, you must set  <i>OutputBuffer</i> to NULL and  <i>OutputBufferLength</i> to 0.  


### -param ResultLength [out, optional]

Pointer to a ULONG variable that receives the actual number of bytes in the buffer pointed to by <i>OutputBuffer</i>.   The caller can pass NULL in <i>ResultLength</i>. If <i>ResultLength</i> is not NULL, the received value is less than or equal to the <i>OutputBufferLength</i> value.


## -returns



The <b>USBD_QueryUsbCapability</b> routine returns an NT status code.  

Possible values include, but are not limited to, the status codes listed in the following table. 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful and the specified capability is supported.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller passed an invalid parameter value.

<ul>
<li><i>USBDHandle</i> or  <i>CapabilityType</i> is NULL.</li>
<li><i>OutputBuffer</i> is NULL but <i>OutputBufferLength</i> indicates a nonzero value. Conversely, the caller provided an output buffer but the buffer length is 0.</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The specified capability is not supported by the underlying USB driver stack.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The specified capability is not supported either by the host controller hardware or the USB driver stack.

</td>
</tr>
</table>
 




## -remarks



Windows 8 includes a new USB driver stack to support USB 3.0 devices. The new USB driver stack provides several  new capabilities defined such as, stream support and chained MDLs that can be used by a client driver.

A client driver can determine the version of the underlying USB driver stack by calling the <a href="..\usbdlib\nf-usbdlib-usbd_isinterfaceversionsupported.md">IsInterfaceVersionSupported</a> routine. 

The client driver can use the new capabilities <i>only if</i> the underlying USB driver stack <i>and</i> hardware support them.  For example, in order to send I/O requests to a particular stream associated with a bulk endpoint, the underlying USB driver stack, the endpoint, and the host controller hardware must support the static streams capability. The client driver <i>must not</i> call <a href="..\usbdlib\nf-usbdlib-usbd_isinterfaceversionsupported.md">IsInterfaceVersionSupported</a>  and assume the capabilities of the driver stack. Instead, the client driver <i>must</i>  always call  <b>USBD_QueryUsbCapability</b> to determine whether the USB driver stack and hardware support a particular capability. 

The following table describes the USB-specific capabilities that a client driver can query through a <b>USBD_QueryUsbCapability</b> call. 

<table>
<tr>
<th>Capability GUID</th>
<th>Description</th>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_CHAINED_MDLS</td>
<td>
If the USB driver stack supports chained MDLs, the client driver can provide the transfer data as a chain of MDLs  that reference segmented buffers in physical memory. For more information, see <a href="..\wdm\ns-wdm-_mdl.md">MDL</a>. Chained MDLs preclude the need for allocating and copying memory to create virtually contiguous buffers and therefore make I/O transfers more efficient. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450848">How to Send Chained MDLs</a>.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_STATIC_STREAMS</td>
<td>
If supported, the client driver can send I/O requests to streams in a bulk endpoint.

For the static streams query request, the client driver is required to provide an output buffer (USHORT). After the call completes and if the static streams capability is supported, the output buffer receives the maximum number of supported streams by the host controller. 

The output buffer value does not indicate the maximum number of streams supported by the bulk endpoint in the device. To determine that number, the client driver must inspect the endpoint companion descriptor.

The USB driver stack  in Windows 8 supports up to 255 streams. 

If static streams are supported, the client driver can send I/O requests to the first stream (also called the <i>default stream</i>) by using the pipe handle obtained through a select-configuration request. For other streams in the endpoint, the client driver must open those streams and obtain pipe handles for them in order to send I/O requests. For more information about opening streams, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_FUNCTION_SUSPEND</td>
<td>
This capability determines whether the underlying USB driver stack supports USB Function Suspend and Remote Wake-Up features. If supported, the driver stack can process a resume signal (for remote wake-up)  from an individual function in a USB 3.0 composite device. Based on that signal, an individual function driver can exit the low-power state of its function.

The capability is intended to be used by a composite driver: the driver that is loaded as the function device object (FDO) in the device stack for the  composite device. By default, the Microsoft-provided USB Generic Parent Driver (Usbccgp.sys) is loaded as the FDO. 

If your driver replaces  Usbccgp.sys, the driver must be able to request remote wake-up and propagate the resume signal from the USB driver stack. Before implementing that logic, the driver must determine the USB driver stack's support for the function suspend capability by calling <b>USBD_QueryUsbCapability</b>. Usbccgp.sys in Windows 8 implements function suspend.

For a code example and more information about function suspend, see <a href="https://msdn.microsoft.com/91F96D30-CD18-4DDC-BA5A-7BFFA8FBED9B">How to Implement Function Suspend in a Composite Driver</a>.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_SELECTIVE_SUSPEND</td>
<td>
Determines whether the underlying USB driver stack supports selective suspend.

For information about selective suspend, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540144">USB Selective Suspend</a>.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE</td>
<td>
Determines whether the bus is operating at high-speed or higher. 

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE</td>
<td>
Determines whether the bus is operating at SuperSpeed or higher.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_TIME_SYNC</td>
<td>
Determines whether the frame number and QPC association feature is supported 
    on the controller. 

</td>
</tr>
</table>
 


#### Examples

The code snippet shows how to call <b>USBD_QueryUsbCapability</b> to determine the capabilities of the underlying USB driver stack.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>
/*++

Routine Description:
This helper routine queries the underlying USB driver stack
for specific capabilities. This code snippet assumes that 
USBD handle was retrieved by the client driver in a 
previous call to the USBD_CreateHandle routine.

Parameters:

fdo: Pointer to the device object that is the current top
of the stack as reported by IoAttachDeviceToDeviceStack.

Return Value: VOID
--*/

VOID QueryUsbDriverStackCaps (PDEVICE_OBJECT fdo)
{
    NTSTATUS ntStatus = STATUS_SUCCESS;   
    PDEVICE_EXTENSION deviceExtension;

    deviceExtension = (PDEVICE_EXTENSION)fdo-&gt;DeviceExtension;

    if (!deviceExtension-&gt;UsbdHandle)
    {
        return;
    }

    // Check if the underlying USB driver stack
    // supports USB 3.0 devices.

    if (!USBD_IsInterfaceVersionSupported(
        deviceExtension-&gt;UsbdHandle,                                       
        USBD_INTERFACE_VERSION_602))
    {
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Old USB stack loaded.\n" ));
    }
    else
    {
        // Call USBD_QueryUsbCapability to determine 
        // function suspend support.     
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "New USB stack loaded.\n" ));
        ntStatus = USBD_QueryUsbCapability ( deviceExtension-&gt;UsbdHandle,  
            (GUID*)&amp;GUID_USB_CAPABILITY_FUNCTION_SUSPEND,  
            0,  
            NULL,
            NULL);

        if (NT_SUCCESS(ntStatus)) 
        {
            deviceExtension-&gt;FunctionSuspendSupported = TRUE;
            KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Function suspend supported.\n" ));
        } 
        else 
        {
            deviceExtension-&gt;FunctionSuspendSupported  = FALSE;
            ntStatus = STATUS_SUCCESS;
            KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Function suspend not supported.\n" ));
        }
    }

    // Call USBD_QueryUsbCapability to determine 
    // chained MDL support. 

    ntStatus = USBD_QueryUsbCapability(
        deviceExtension-&gt;UsbdHandle,
        (GUID*)&amp;GUID_USB_CAPABILITY_CHAINED_MDLS,
        0,
        NULL,
        NULL);

    if (NT_SUCCESS(ntStatus)) 
    {
        deviceExtension-&gt;ChainedMDLSupport = TRUE;
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Chained MDLs supported.\n" ));
    } 
    else 
    {
        deviceExtension-&gt;ChainedMDLSupport = FALSE;
        ntStatus = STATUS_SUCCESS;
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Chained MDLs not supported.\n" ));
    }

    // Call USBD_QueryUsbCapability to determine 
    // stream support. 

    ntStatus = USBD_QueryUsbCapability (deviceExtension-&gt;UsbdHandle, 
        (GUID*)&amp;GUID_USB_CAPABILITY_STATIC_STREAMS, 
        sizeof(ULONG), 
        (PUCHAR) &amp;deviceExtension-&gt;MaxSupportedStreams, 
        NULL);  


    if (!NT_SUCCESS(ntStatus)) 
    {
        deviceExtension-&gt;MaxSupportedStreams = 0;
        ntStatus = STATUS_SUCCESS;
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Static streams not supported.\n" ));
    }

    // Call USBD_QueryUsbCapability to determine 
    // selective suspend support. 

    ntStatus = USBD_QueryUsbCapability (deviceExtension-&gt;UsbdHandle, 
        (GUID*)&amp;GUID_USB_CAPABILITY_SELECTIVE_SUSPEND, 
        0, 
        NULL, 
        NULL);

    if (!NT_SUCCESS(ntStatus)) 
    {
        ntStatus = STATUS_SUCCESS;
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Selective suspend not supported.\n" ));
    }
    else
    {
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "Selective suspend supported.\n" ));
    }

    // Call USBD_QueryUsbCapability to determine 
    // device speed. 
    ntStatus = USBD_QueryUsbCapability (deviceExtension-&gt;UsbdHandle, 
        (GUID*)&amp;GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE, 
        0, 
        NULL, 
        NULL);

    if (!NT_SUCCESS(ntStatus)) 
    {
        ntStatus = STATUS_SUCCESS;
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "The device is operating at full speed or lower.\n The device can operate at high speed or higher." ));
    }
    else
    {
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "The device is operating at high speed or higher.\n" ));
    }

    // Call USBD_QueryUsbCapability to determine 
    // device speed. 
    ntStatus = USBD_QueryUsbCapability (deviceExtension-&gt;UsbdHandle, 
        (GUID*)&amp;GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE, 
        0, 
        NULL, 
        NULL);

    if (!NT_SUCCESS(ntStatus)) 
    {
        ntStatus = STATUS_SUCCESS;
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "The device is operating at high speed or lower.\n The device can operate at Superspeed or higher." ));
    }
    else
    {
        KdPrintEx(( DPFLTR_IHVDRIVER_ID, DPFLTR_INFO_LEVEL, "The device is operating at SuperSpeed or higher.\n" ));
    }

    return;

}
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_QueryUsbCapability routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

