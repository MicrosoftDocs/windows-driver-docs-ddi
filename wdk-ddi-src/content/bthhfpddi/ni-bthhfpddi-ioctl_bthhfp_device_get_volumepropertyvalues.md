---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
title: IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES (bthhfpddi.h)
description: The IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL returns KSPROPERTY_VALUES data for the KSPROPERTY_AUDIO_VOLUMELEVEL property.
old-location: audio\ioctl_bthhfp_device_get_volumepropertyvalues.htm
tech.root: audio
ms.assetid: 56DA61CB-D4D3-40DF-861D-2A2EE257C194
ms.date: 05/08/2018
keywords: ["IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL"]
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES, IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES control, IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES control code [Audio Devices], audio.ioctl_bthhfp_device_get_volumepropertyvalues, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
f1_keywords:
 - "bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES"
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
- IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL


## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</b> 
   IOCTL returns <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a> data for the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksproperty-audio-volumelevel">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

A buffer containing a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a> structure followed by any other data referenced by this structure.


### -output-buffer-length

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a> structure and referenced data.


### -in-out-buffer








### -inout-buffer-length








### -status-block

N/A


## -remarks



The audio driver’s KS filter topology includes a KS node of type <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a> for both input and output if the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthhfpddi/ns-bthhfpddi-_bthhfp_descriptor">BTHHFP_DESCRIPTOR</a> descriptor indicates volume support. The audio driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksnode_descriptor">KSNODE_DESCRIPTOR</a> structure for this node includes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_item">PKSPROPERTY_ITEM</a> for the <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property. The audio driver sets the <b>PKSPROPERTY_ITEM</b>.<i>Values</i> member to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a> structured returned by this request.

This allows the Handsfree proofile (HFP) driver to almost entirely handle the problem of mapping <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property values to the Bluetooth Handsfree profile. The audio driver’s property Get and Set handlers for this property simply call the HFP driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/bluetooth-hfp-ddi-ioctls">Bluetooth HFP DDI IOCTLs</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/audio/ksnodetype-volume">KSNODETYPE_VOLUME</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksnode_descriptor">KSNODE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksproperty_values">KSPROPERTY_VALUES</a>
 

 

