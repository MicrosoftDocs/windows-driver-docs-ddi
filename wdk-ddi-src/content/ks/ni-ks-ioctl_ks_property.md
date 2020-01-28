---
UID: NI:ks.IOCTL_KS_PROPERTY
title: IOCTL_KS_PROPERTY (ks.h)
description: An application can use IOCTL_KS_PROPERTY to get or set properties, or to determine the properties supported by a KS object. The application passes IOCTL_KS_PROPERTY with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_property.htm
tech.root: stream
ms.assetid: 66f29543-9677-4bae-baa4-6be8ebc52b66
ms.date: 04/23/2018
ms.keywords: IOCTL_KS_PROPERTY, IOCTL_KS_PROPERTY control, IOCTL_KS_PROPERTY control code [Streaming Media Devices], ks-ioctl_58152402-30ed-4938-af47-9e6a1838fec1.xml, ks/IOCTL_KS_PROPERTY, stream.ioctl_ks_property
f1_keywords:
 - "ks/IOCTL_KS_PROPERTY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- IOCTL_KS_PROPERTY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_PROPERTY IOCTL


## -description



An application can use IOCTL_KS_PROPERTY to get or set properties, or to determine the properties supported by a KS object. The application passes IOCTL_KS_PROPERTY with the parameters described below to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-kssynchronousdevicecontrol">KsSynchronousDeviceControl</a> function.




## -ioctlparameters




### -input-buffer

The contents of the client-specified <b>InBuffer</b> parameter depend on the property request, and are documented for each property set. For instance, clients requesting properties in the <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-pin">KSPROPSETID_Pin</a> property set specify a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_pin">KSP_PIN</a> structure. 


### -input-buffer-length

The application places the size, in bytes, of the input buffer contents in the <b>InLength</b> parameter.


### -output-buffer

Similarly, the type of output buffer required also depends on the property request. 


### -output-buffer-length

The application places the size, in bytes, of the output buffer in the <b>OutLength</b> parameter.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -remarks



For more information about input and output buffers and their sizes, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ks-properties">KS Properties</a>.

Filters and pins support property sets using the <b>IOCTL_KS_PROPERTY</b> device I/O control. Although this IOCTL is defined with the METHOD_NEITHER flag, the property data is passed as the output buffer to the IOCTL and probed for read access. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kspropertyhandler">KsPropertyHandler</a> function handles properties requested through <b>IOCTL_KS_PROPERTY</b>.

For a list of valid flags and corresponding descriptions, see the reference page for the <a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a> structure.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff564262(v=vs.85)">KSPROPERTY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_description">KSPROPERTY_DESCRIPTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item">KSPROPERTY_ITEM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_membersheader">KSPROPERTY_MEMBERSHEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_set">KSPROPERTY_SET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a>
 

 

