---
UID: NI:ks.IOCTL_KS_PROPERTY
title: IOCTL_KS_PROPERTY
author: windows-driver-content
description: An application can use IOCTL_KS_PROPERTY to get or set properties, or to determine the properties supported by a KS object. The application passes IOCTL_KS_PROPERTY with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_property.htm
old-project: stream
ms.assetid: 66f29543-9677-4bae-baa4-6be8ebc52b66
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ioctl_ks_property, IOCTL_KS_PROPERTY control code [Streaming Media Devices], IOCTL_KS_PROPERTY, ks/IOCTL_KS_PROPERTY, ks-ioctl_58152402-30ed-4938-af47-9e6a1838fec1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	IOCTL_KS_PROPERTY
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_PROPERTY IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



An application can use IOCTL_KS_PROPERTY to get or set properties, or to determine the properties supported by a KS object. The application passes IOCTL_KS_PROPERTY with the parameters described below to the <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a> function.




## -ioctlparameters




### -input-buffer

The contents of the client-specified <b>InBuffer</b> parameter depend on the property request, and are documented for each property set. For instance, clients requesting properties in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566584">KSPROPSETID_Pin</a> property set specify a pointer to a <a href="..\ks\ns-ks-ksp_pin.md">KSP_PIN</a> structure. 


### -input-buffer-length

The application places the size, in bytes, of the input buffer contents in the <b>InLength</b> parameter.


### -output-buffer

Similarly, the type of output buffer required also depends on the property request. 


### -output-buffer-length

The application places the size, in bytes, of the output buffer in the <b>OutLength</b> parameter.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -remarks


For more information about input and output buffers and their sizes, see <a href="https://msdn.microsoft.com/a385929e-1934-4d88-aaf9-ff1ddbfd30f7">KS Properties</a>.

Filters and pins support property sets using the <b>IOCTL_KS_PROPERTY</b> device I/O control. Although this IOCTL is defined with the METHOD_NEITHER flag, the property data is passed as the output buffer to the IOCTL and probed for read access. The <a href="..\ks\nf-ks-kspropertyhandler.md">KsPropertyHandler</a> function handles properties requested through <b>IOCTL_KS_PROPERTY</b>.

For a list of valid flags and corresponding descriptions, see the reference page for the <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure.



## -see-also

<a href="..\ks\ns-ks-ksproperty_item.md">KSPROPERTY_ITEM</a>

<a href="..\ks\ns-ks-ksproperty_values.md">KSPROPERTY_VALUES</a>

<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>

<a href="..\ks\ns-ks-ksproperty_description.md">KSPROPERTY_DESCRIPTION</a>

<a href="..\ks\ns-ks-ksproperty_set.md">KSPROPERTY_SET</a>

<a href="..\ks\ns-ks-ksproperty_membersheader.md">KSPROPERTY_MEMBERSHEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_PROPERTY control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

