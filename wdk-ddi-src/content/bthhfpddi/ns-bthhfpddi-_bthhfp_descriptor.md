---
UID: NS:bthhfpddi._BTHHFP_DESCRIPTOR
title: "_BTHHFP_DESCRIPTOR"
author: windows-driver-content
description: The BTHHFP_DESCRIPTOR data structure stores information describing a paired Handsfree profile (HFP) device.
old-location: audio\bthhfp_descriptor.htm
old-project: audio
ms.assetid: A3C1E53B-2E41-437A-8613-C43DCD4768B5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: bthhfpddi/BTHHFP_DESCRIPTOR, _BTHHFP_DESCRIPTOR, PBTHHFP_DESCRIPTOR structure pointer [Audio Devices], BTHHFP_DESCRIPTOR, *PBTHHFP_DESCRIPTOR, bthhfpddi/PBTHHFP_DESCRIPTOR, BTHHFP_DESCRIPTOR structure [Audio Devices], audio.bthhfp_descriptor, PBTHHFP_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bthhfpddi.h
apiname:
-	BTHHFP_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PBTHHFP_DESCRIPTOR, BTHHFP_DESCRIPTOR"
---

# _BTHHFP_DESCRIPTOR structure


## -description


The BTHHFP_DESCRIPTOR  data structure stores information describing a paired Handsfree profile (HFP) device.

The HFP driver returns this data structure in the output buffer for the <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a> request.


## -syntax


````
typedef struct _BTHHFP_DESCRIPTOR {
  GUID           InputPinCategory;
  GUID           OutputPinCategory;
  GUID           ContainerId;
  BOOL           SupportsVolume;
  ULONG          VolumePropertyValuesSize;
  UNICODE_STRING FriendlyName;
} BTHHFP_DESCRIPTOR, *PBTHHFP_DESCRIPTOR;
````


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

If remote volume control is supported, this member contains the size of the data returned by the <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues.md">IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</a> request.


### -field FriendlyName

An indirect string identifying the human readable friendly name of the paired HFP device.


## -remarks


The HFP driver calculates the <i>InputPinCategory</i> and <i>OutputPinCategory</i> GUIDs based on the 'Bluetooth Class of Device' data that is contained in the SDP information of the paired device. The audio driver sets the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563533(v=vs.85).aspx">KSPIN_DESCRIPTOR.Category</a> members for the input and output bridge pins to the calculated GUIDs.
<div class="alert"><b>Note</b>  <p class="note">In some cases the input and output pin categories may be the same.

<p class="note">The audio driver should make no particular assumptions about the category GUID values returned in <i>InputPinCategory</i> and <i>OutputPinCategory</i> members. The audio system uses this information to help determine the type of device (for example, headset versus speakers) and whether to use the device for different purposes such as the default communications device.

</div><div> </div>The audio driver stores the <i>ContainerId</i> in appropriate context data, and returns this value in its implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265129">KSPROPERTY_JACK_CONTAINERID</a> KS property.

If <i>SupportsVolume</i> is true, the audio driver includes volume support in its KS topology.

The audio driver uses the string returned in <i>FriendlyName</i> to set the DEVPKEY_DeviceInterface_FriendlyName property on the KS filter’s KSCATEGORY_AUDIO device interface. To do this, the audio driver calls IoSetDeviceInterfacePropertyData and sets the property type to DEVPROP_TYPE_STRING_INDIRECT. An example string is "@System32\drivers\bthhfenum.sys,#2;%1 Hands-Free%0..;(SomeDeviceName)”. Note that this is an indirect string and therefore not necessarily the human readable string that is directly displayed in a user interface. The audio system uses this string to generate localized strings used for display to the user, such as in the Sounds control panel.

For information about the IOCTLs that work with this structure, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302029">Bluetooth HFP DDI Structures</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265129">KSPROPERTY_JACK_CONTAINERID</a>

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563533(v=vs.85).aspx">KSPIN_DESCRIPTOR.Category</a>

<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>

<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues.md">IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20BTHHFP_DESCRIPTOR structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

