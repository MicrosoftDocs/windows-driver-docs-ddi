---
UID: NS:bthhfpddi._BTHHFP_DESCRIPTOR2
title: "_BTHHFP_DESCRIPTOR2"
author: windows-driver-content
description: The BTHHFP_DESCRIPTOR2 data structure stores information describing a paired Handsfree profile (HFP) device.
old-location: audio\bthhfp_descriptor2.htm
old-project: audio
ms.assetid: A455F181-E1DB-47CC-96E5-AE72988366F3
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: BTHHFP_DESCRIPTOR2, PBTHHFP_DESCRIPTOR2 structure pointer [Audio Devices], PBTHHFP_DESCRIPTOR2, bthhfpddi/PBTHHFP_DESCRIPTOR2, _BTHHFP_DESCRIPTOR2, bthhfpddi/BTHHFP_DESCRIPTOR2, audio.bthhfp_descriptor2, *PBTHHFP_DESCRIPTOR2, BTHHFP_DESCRIPTOR2 structure [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	BTHHFP_DESCRIPTOR2
product: Windows
targetos: Windows
req.typenames: BTHHFP_DESCRIPTOR2, *PBTHHFP_DESCRIPTOR2
---

# _BTHHFP_DESCRIPTOR2 structure


## -description


The BTHHFP_DESCRIPTOR2  data structure stores information describing a paired Handsfree profile (HFP) device.

The HFP driver returns this data structure in the output buffer for the <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor2.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2</a> request.


## -syntax


````
typedef struct _BTHHFP_DESCRIPTOR2 {
  GUID           InputPinCategory;
  GUID           OutputPinCategory;
  GUID           ContainerId;
  BOOL           SupportsVolume;
  ULONG          VolumePropertyValuesSize;
  UNICODE_STRING FriendlyName;
  BOOL           SupportsNREC;
} BTHHFP_DESCRIPTOR2, *PBTHHFP_DESCRIPTOR2;
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


### -field SupportsNREC

Indicates whether the paired HFP device supports noise reduction / echo cancellation (NREC).


## -remarks



When the <i>SupportsNREC</i> parameter's value is TRUE, the audio driver should not support RAW mode pins. In this mode, the audio driver cannot support RAW mode pins because the remote Bluetooth device can enable its internal NREC processing at any time.


When <i>SupportsNREC</i> is set to FALSE, the audio driver should support RAW mode pins. The driver can, optionally, also support non-RAW modes and provide its own signal processing. In this case, the driver can provide signal processing  in one of three ways: within the driver code itself; by using its digital signal processing (DSP) module; by using its associated audio processing object (APO).





## -see-also

<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor2.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302029">Bluetooth HFP DDI Structures</a>



<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_volumepropertyvalues.md">IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20BTHHFP_DESCRIPTOR2 structure%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

