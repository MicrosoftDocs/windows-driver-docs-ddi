---
UID: NS:bthhfpddi._BTHHFP_DESCRIPTOR
title: _BTHHFP_DESCRIPTOR (bthhfpddi.h)
description: The BTHHFP_DESCRIPTOR data structure stores information describing a paired Handsfree profile (HFP) device.
old-location: audio\bthhfp_descriptor.htm
tech.root: audio
ms.assetid: A3C1E53B-2E41-437A-8613-C43DCD4768B5
ms.date: 05/08/2018
ms.keywords: "*PBTHHFP_DESCRIPTOR, BTHHFP_DESCRIPTOR, BTHHFP_DESCRIPTOR structure [Audio Devices], PBTHHFP_DESCRIPTOR, PBTHHFP_DESCRIPTOR structure pointer [Audio Devices], _BTHHFP_DESCRIPTOR, audio.bthhfp_descriptor, bthhfpddi/BTHHFP_DESCRIPTOR, bthhfpddi/PBTHHFP_DESCRIPTOR"
ms.topic: struct
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- Bthhfpddi.h
api_name:
- BTHHFP_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: BTHHFP_DESCRIPTOR, *PBTHHFP_DESCRIPTOR
---

# _BTHHFP_DESCRIPTOR structure


## -description


The BTHHFP_DESCRIPTOR  data structure stores information describing a paired Handsfree profile (HFP) device.

The HFP driver returns this data structure in the output buffer for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a> request.


## -struct-fields




### -field InputPinCategory

KS pin category for the input function of the paired HFP device.


### -field OutputPinCategory

KS pin category for the output function of the paired HFP device.


### -field ContainerId

The PnP container ID for the paired HFP device.


### -field SupportsVolume

Indicates whether the paired HFP device supports remote volume control.


### -field VolumePropertyValuesSize

If remote volume control is supported, this member contains the size of the data returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues">IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</a> request.


### -field FriendlyName

An indirect string identifying the human readable friendly name of the paired HFP device.


## -remarks



The HFP driver calculates the <i>InputPinCategory</i> and <i>OutputPinCategory</i> GUIDs based on the 'Bluetooth Class of Device' data that is contained in the SDP information of the paired device. The audio driver sets the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kspin_descriptor">KSPIN_DESCRIPTOR.Category</a> members for the input and output bridge pins to the calculated GUIDs.

<div class="alert"><b>Note</b>  <p class="note">In some cases the input and output pin categories may be the same.

<p class="note">The audio driver should make no particular assumptions about the category GUID values returned in <i>InputPinCategory</i> and <i>OutputPinCategory</i> members. The audio system uses this information to help determine the type of device (for example, headset versus speakers) and whether to use the device for different purposes such as the default communications device.

</div>
<div> </div>
The audio driver stores the <i>ContainerId</i> in appropriate context data, and returns this value in its implementation of the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-jack-containerid">KSPROPERTY_JACK_CONTAINERID</a> KS property.

If <i>SupportsVolume</i> is true, the audio driver includes volume support in its KS topology.

The audio driver uses the string returned in <i>FriendlyName</i> to set the DEVPKEY_DeviceInterface_FriendlyName property on the KS filter’s KSCATEGORY_AUDIO device interface. To do this, the audio driver calls IoSetDeviceInterfacePropertyData and sets the property type to DEVPROP_TYPE_STRING_INDIRECT. An example string is "@System32\drivers\bthhfenum.sys,#2;%1 Hands-Free%0..;(SomeDeviceName)”. Note that this is an indirect string and therefore not necessarily the human readable string that is directly displayed in a user interface. The audio system uses this string to generate localized strings used for display to the user, such as in the Sounds control panel.

For information about the IOCTLs that work with this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-structures">Bluetooth HFP DDI Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/bthhfpddi/ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues">IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-kspin_descriptor">KSPIN_DESCRIPTOR.Category</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-jack-containerid">KSPROPERTY_JACK_CONTAINERID</a>
 

 

