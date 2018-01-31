---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
title: IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL returns KSPROPERTY_VALUES data for the KSPROPERTY_AUDIO_VOLUMELEVEL property.
old-location: audio\ioctl_bthhfp_device_get_volumepropertyvalues.htm
old-project: audio
ms.assetid: 56DA61CB-D4D3-40DF-861D-2A2EE257C194
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.ioctl_bthhfp_device_get_volumepropertyvalues, IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES control code [Audio Devices], IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES</b> 
   IOCTL returns <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> data for the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537309">KSPROPERTY_AUDIO_VOLUMELEVEL</a> property.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

A buffer containing a <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> structure followed by any other data referenced by this structure.


### -output-buffer-length

The size of a <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> structure and referenced data.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

N/A


## -remarks


The audio driver’s KS filter topology includes a KS node of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a> for both input and output if the <a href="..\bthhfpddi\ns-bthhfpddi-_bthhfp_descriptor.md">BTHHFP_DESCRIPTOR</a> descriptor indicates volume support. The audio driver’s <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563473(v=vs.85).aspx">KSNODE_DESCRIPTOR</a> structure for this node includes a <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565176(v=vs.85).aspx">PKSPROPERTY_ITEM</a> for the <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property. The audio driver sets the <b>PKSPROPERTY_ITEM</b>.<i>Values</i> member to the <a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a> structured returned by this request.

This allows the Handsfree proofile (HFP) driver to almost entirely handle the problem of mapping <b>KSPROPERTY_AUDIO_VOLUMELEVEL</b> property values to the Bluetooth Handsfree profile. The audio driver’s property Get and Set handlers for this property simply call the HFP driver.



## -see-also

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff565966(v=vs.85).aspx">KSPROPERTY_VALUES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537208">KSNODETYPE_VOLUME</a>

<a href="http://msdn.microsoft.com/en-us/library/windows/hardware/ff563473(v=vs.85).aspx">KSNODE_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_GET_VOLUMEPROPERTYVALUES control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

