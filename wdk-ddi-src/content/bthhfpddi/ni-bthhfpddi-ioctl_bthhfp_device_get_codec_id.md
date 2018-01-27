---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
title: IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
author: windows-driver-content
description: An audio driver can send an IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code to query the Bluetooth driver stack about the codec ID used by the HFP service. This helps the audio driver determine the sampling rate for the data.
old-location: audio\ioctl_bthhfp_device_get_codec_id.htm
old-project: audio
ms.assetid: 38B67F0E-46A4-4AB5-B122-F5DE282FE52D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.ioctl_bthhfp_device_get_codec_id, IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code [Audio Devices], IOCTL_BTHHFP_DEVICE_GET_CODEC_ID, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	IOCTL_BTHHFP_DEVICE_GET_CODEC_ID
product: Windows
targetos: Windows
req.typenames: *PHFP_BYPASS_CODEC_ID_VERSION, HFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_CODEC_ID IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


An audio driver can send an <b>IOCTL_BTHHFP_DEVICE_GET_CODEC_ID</b> 
   control code to query the Bluetooth driver stack about the codec ID used by the HFP service. This helps the audio driver determine the sampling rate for the data.


## -ioctlparameters




### -input-buffer

An <a href="..\bthhfpddi\ne-bthhfpddi-_hfp_bypass_codec_id_version.md">HFP_BYPASS_CODEC_ID_VERSION</a> enumeration value. Currently, only REQ_HFP_BYPASS_CODEC_ID_V1 is supported.


### -input-buffer-length

The size of an <a href="..\bthhfpddi\ne-bthhfpddi-_hfp_bypass_codec_id_version.md">HFP_BYPASS_CODEC_ID_VERSION</a> enumeration value.


### -output-buffer

A codec ID structure containing the codec ID information. Currently, only <a href="..\bthhfpddi\ns-bthhfpddi-_hfp_bypass_codec_id_v1.md">HFP_BYPASS_CODEC_ID_V1</a> is supported.


### -output-buffer-length

The size of a codec ID structure.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the codec ID.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_GET_CODEC_ID control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

