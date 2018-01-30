---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2
title: IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2
author: windows-driver-content
description: The IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 IOCTL Gets descriptive information about the paired Handsfree profile (HFP) device.
old-location: audio\ioctl_bthhfp_device_get_descriptor2.htm
old-project: audio
ms.assetid: B72D0236-1C2B-4D0B-86B4-4E9B667BA1B3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audio.ioctl_bthhfp_device_get_descriptor2, IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 control code [Audio Devices], IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2</b> 
   IOCTL Gets descriptive information about the paired Handsfree profile (HFP) device.

This IOCTL is available in Windows 8.1 and later operating systems, and it supersedes <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>.


## -ioctlparameters




### -input-buffer

None


### -input-buffer-length

None


### -output-buffer

A buffer containing a <a href="..\bthhfpddi\ns-bthhfpddi-_bthhfp_descriptor2.md">BTHHFP_DESCRIPTOR2</a> structure followed by any other data that is referenced by the structure. This is true,  if the output buffer size is sufficient and the request succeeds. In particular, the buffer includes storage for the string that is referenced by the <i>FriendlyName</i> field of the <b>BTHHFP_DESCRIPTOR2</b> structure.


### -output-buffer-length

The size of a <b>BTHHFP_DESCRIPTOR2</b> structure and referenced data.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the number of bytes that the routine writes to the output buffer. Note this can be larger than the size of the <b>BTHHFP_DESCRIPTOR2</b> structure, as the output buffer may contain other data referenced by the <b>BTHHFP_DESCRIPTOR2</b> structure.

If Status is set to STATUS_BUFFER_TOO_SMALL, then <i>Information</i> is the size of the buffer that the caller should allocate for this request.


## -remarks


The audio driver sends this request to obtain information about an enabled GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS device interface. The information does not change while the interface is enabled, but can change while the interface is disabled. Therefore the audio driver sends this request shortly after discovering an enabled device interface and uses the information to build an appropriate KSFILTER_DESCRIPTOR structure.

The audio driver sends this request once with an output buffer size of zero (0) in order to determine the required output buffer size. In this case, the request will complete with Status STATUS_BUFFER_TOO_SMALL and the <i>Information</i> parameter will  contain the required buffer size. The audio driver then allocates the necessary storage and sends the request again. Typically an audio driver will keep a pointer to this storage location in its device context for reference during later activity.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>

<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_descriptor.md">IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</a>

<a href="..\bthhfpddi\ns-bthhfpddi-_bthhfp_descriptor2.md">BTHHFP_DESCRIPTOR2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR2 control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

