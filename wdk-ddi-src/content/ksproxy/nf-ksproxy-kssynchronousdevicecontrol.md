---
UID: NF:ksproxy.KsSynchronousDeviceControl
title: KsSynchronousDeviceControl function
author: windows-driver-content
description: The KsSynchronousDeviceControl function issues a synchronous device I/O control operation to the KS object that is specified by a file handle.
old-location: stream\kssynchronousdevicecontrol.htm
old-project: stream
ms.assetid: 82c8f0c0-d9df-4f0d-8a45-dda8fa8a132a
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KsSynchronousDeviceControl, ksproxy/KsSynchronousDeviceControl, stream.kssynchronousdevicecontrol, KsSynchronousDeviceControl function [Streaming Media Devices], ksproxy_5bfad2d0-2ee7-476d-a67b-e7c877505280.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Ksproxy.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ksproxy.lib
-	Ksproxy.dll
apiname:
-	KsSynchronousDeviceControl
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# KsSynchronousDeviceControl function


## -description


The <b>KsSynchronousDeviceControl</b> function issues a synchronous device I/O control operation to the KS object that is specified by a file handle. 


## -syntax


````
HRESULT KsSynchronousDeviceControl(
  _In_      HANDLE Handle,
  _In_      ULONG  IoControl,
  _In_opt_  PVOID  InBuffer,
  _In_      ULONG  InLength,
  _Out_opt_ PVOID  OutBuffer,
  _In_      ULONG  OutLength,
  _Inout_   PULONG BytesReturned
);
````


## -parameters




### -param Handle [in]

Handle to the KS object on which to perform the operation.


### -param IoControl [in]

Control code that identifies a specific type of operation to perform on a KS object. 


### -param InBuffer [in, optional]

Pointer to a buffer that contains data that specifies the operation to perform. 


### -param InLength [in]

Size, in bytes, of the buffer at <i>InBuffer</i>.


### -param OutBuffer [out, optional]

Pointer to a buffer that contains either data for the operation or buffer space that receives data for the operation. 


### -param OutLength [in]

Size, in bytes, of the buffer at <i>OutBuffer</i>.


### -param BytesReturned [in, out]

Pointer to a variable that receives the size, in bytes, of the data that <b>KsSynchronousDeviceControl</b> stores in the buffer at <i>OutBuffer</i>. 


## -returns



Returns NOERROR if successful; otherwise, returns an error code.




## -remarks



To retrieve the handle to the KS object, an application should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559890">IKsObject::KsGetObjectHandle</a> method. 

An application can set the control code in <i>IoControl</i> and the buffers at <i>InBuffer</i> and <i>OutBuffer</i> as follows to specify the operation to perform: 

<ul>
<li>
Set <i>IoControl</i> to <a href="..\ks\ni-ks-ioctl_ks_property.md">IOCTL_KS_PROPERTY</a> to access a property. Set <i>InBuffer</i> to point to a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that specifies the property of the property set to access and whether to retrieve information about the property or set information in the property. To set information in the property, set <i>OutBuffer</i> to point to that information. To retrieve information from the property, set <i>OutBuffer</i> to receive that information. 

</li>
<li>
Set <i>IoControl</i> to <a href="..\ks\ni-ks-ioctl_ks_method.md">IOCTL_KS_METHOD</a> to execute a method. Set <i>InBuffer</i> to point to a <a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a> structure that specifies the method of the method set to execute and whether to read and/or write data related to the method. To read data, set <i>OutBuffer</i> to point to that data. To write data, set <i>OutBuffer</i> to receive that data.

</li>
<li>
Set <i>IoControl</i> to <a href="..\ks\ni-ks-ioctl_ks_enable_event.md">IOCTL_KS_ENABLE_EVENT</a> to request that the KS object specified by <i>Handle</i> notify the application whenever a specific event action occurs. Set <i>InBuffer</i> to point to a <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a> structure that specifies the event of the event set about which to notify. Set <i>OutBuffer</i> to point to a <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that describes how the KS object should notify the application when the event occurs. Also see <a href="https://msdn.microsoft.com/3eaa1d65-8417-4a07-b358-823394baec9b">KS Events</a>.

</li>
<li>
Set <i>IoControl</i> to <a href="..\ks\ni-ks-ioctl_ks_disable_event.md">IOCTL_KS_DISABLE_EVENT</a> to inform the KS object specified by <i>Handle</i> to stop notifying the application whenever a specific event action occurs. Set <i>InBuffer</i> to point to the <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> structure that was previously used in the event-notification request. 

</li>
</ul>
To retrieve a list of all properties, events, or methods supported by a filter, an application can set <i>IoControl</i> to IOCTL_KS_PROPERTY, IOCTL_KS_ENABLE_EVENT, or IOCTL_KS_METHOD. For the KSPROPERTY, KSEVENT, or KSMETHOD structure to which <i>InBuffer</i> points, set the <i>Set</i> member to GUID_NULL and set the <i>Flags</i> member to KSPROPERTY_TYPE_SETSUPPORT.

After the call to <b>KsSynchronousDeviceControl</b>, <i>OutBuffer</i> will contain an array of set GUIDs supported by the object specified by <i>Handle</i>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559890">IKsObject::KsGetObjectHandle</a>



<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>



<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>



<a href="..\ks\ni-ks-ioctl_ks_enable_event.md">IOCTL_KS_ENABLE_EVENT</a>



<a href="..\ks\ni-ks-ioctl_ks_disable_event.md">IOCTL_KS_DISABLE_EVENT</a>



<a href="..\ks\ni-ks-ioctl_ks_method.md">IOCTL_KS_METHOD</a>



<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>



<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>



<a href="..\ks\ni-ks-ioctl_ks_property.md">IOCTL_KS_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsSynchronousDeviceControl function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

