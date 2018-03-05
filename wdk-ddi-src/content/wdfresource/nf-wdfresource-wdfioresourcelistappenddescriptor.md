---
UID: NF:wdfresource.WdfIoResourceListAppendDescriptor
title: WdfIoResourceListAppendDescriptor function
author: windows-driver-content
description: The WdfIoResourceListAppendDescriptor method adds a resource descriptor to the end of a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistappenddescriptor.htm
old-project: wdf
ms.assetid: da9213c1-e519-44ad-aabf-fd05bdbd2079
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_547a6869-7e4a-4140-9851-0b1ca9810eaa.xml, WdfIoResourceListAppendDescriptor, WdfIoResourceListAppendDescriptor method, kmdf.wdfioresourcelistappenddescriptor, wdf.wdfioresourcelistappenddescriptor, wdfresource/WdfIoResourceListAppendDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfresource.h
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
-	WdfIoResourceListAppendDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_SEND_OPTIONS, *PWDF_REQUEST_SEND_OPTIONS
req.product: Windows 10 or later.
---

# WdfIoResourceListAppendDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListAppendDescriptor</b> method adds a resource descriptor to the end of a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.


## -syntax


````
NTSTATUS WdfIoResourceListAppendDescriptor(
  _In_ WDFIORESLIST            ResourceList,
  _In_ PIO_RESOURCE_DESCRIPTOR Descriptor
);
````


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -returns



<b>WdfIoResourceListAppendDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver was not allowed to add descriptors to the logical configuration that the <i>ResourceList</i> parameter specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the descriptor.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



The framework copies the contents of the <a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure that the <i>Descriptor</i> parameter points to into internal storage, so the driver routine that calls <b>WdfIoResourceListAppendDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfIoResourceListAppendDescriptor</b>, the driver can reuse the <b>IO_RESOURCE_DESCRIPTOR</b> structure.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example creates an empty logical configuration and adds it to a resource requirements list. Then, the example initializes a resource descriptor and adds the descriptor to the logical configuration.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_RESOURCE_DESCRIPTOR  descriptor;
NTSTATUS  status;
WDFIORESLIST  logConfig;

status = WdfIoResourceListCreate(
                                 RequirementsList,
                                 WDF_NO_OBJECT_ATTRIBUTES,
                                 &amp;logConfig
                                 );
if (!NT_SUCCESS(status)) {
    return status;
}

status = WdfIoResourceRequirementsListAppendIoResList(
                                                      RequirementsList,
                                                      logConfig
                                                      );
if (!NT_SUCCESS(status)) {
    return status;
}

RtlZeroMemory(
              &amp;descriptor,
              sizeof(descriptor)
              );

descriptor.Option = 0;
descriptor.Type = CmResourceTypePort;
descriptor.ShareDisposition = CmResourceShareDeviceExclusive;
descriptor.Flags = CM_RESOURCE_PORT_IO|CM_RESOURCE_PORT_16_BIT_DECODE;
descriptor.u.Port.Length = 1;
descriptor.u.Port.Alignment = 0x01;
descriptor.u.Port.MinimumAddress.QuadPart = 0;
descriptor.u.Port.MaximumAddress.QuadPart = 0xFFFF;

status = WdfIoResourceListAppendDescriptor(
                                           logConfig,
                                           &amp;descriptor
                                           );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistcreate.md">WdfIoResourceListCreate</a>



<a href="..\wdm\ns-wdm-_io_resource_descriptor.md">IO_RESOURCE_DESCRIPTOR</a>



<a href="..\wdfresource\nf-wdfresource-wdfioresourcelistinsertdescriptor.md">WdfIoResourceListInsertDescriptor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoResourceListAppendDescriptor method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

