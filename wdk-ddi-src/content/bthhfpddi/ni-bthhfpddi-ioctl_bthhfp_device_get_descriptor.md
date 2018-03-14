---
UID: NI:bthhfpddi.IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR
title: IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR
author: windows-driver-content
description: The audio driver issues the IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR control code to get information about an enabled GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS device interface.
old-location: audio\ioctl_bthhfp_device_get_descriptor.htm
old-project: audio
ms.assetid: 94B5E83E-8151-4BD6-9E1E-6C96B460D65F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR, IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR control code [Audio Devices], audio.ioctl_bthhfp_device_get_descriptor, bthhfpddi/IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthhfpddi.h
api_name:
-	IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_VERSION, *PHFP_BYPASS_CODEC_ID_VERSION
---

# IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR IOCTL


## -description


The audio driver issues the <b>IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR</b> 
   control code to get information about an enabled GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS device interface.
<div class="alert"><b>Note</b>  This IOCTL supersedes <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_ksnodetypes.md">IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES</a> and <a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_containerid.md">IOCTL_BTHHFP_DEVICE_GET_CONTAINERID</a> which have now been deprecated.</div><div> </div>

## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

A buffer containing a <a href="..\bthhfpddi\ns-bthhfpddi-_bthhfp_descriptor.md">BTHHFP_DESCRIPTOR</a> structure followed by any other data referenced by the structure. This is true, if the output buffer size is sufficient and the request succeeds. In particular, the buffer includes storage for the string referenced by the <i>FriendlyName</i> field of the <b>BTHHFP_DESCRIPTOR</b> structure.


### -output-buffer-length

The size of a <b>BTHHFP_DESCRIPTOR</b> structure and referenced data.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the routine succeeds, then Status is set to STATUS_SUCCESS and the <i>Information</i> member is the number of bytes that the routine writes to the output buffer.

<div class="alert"><b>Note</b>  This can be larger than the size of the <b>BTHHFP_DESCRIPTOR</b> structure, as the output buffer may contain other data referenced by the structure</div>
<div> </div>
If Status is set to STATUS_BUFFER_TOO_SMALL, then the audio driver should read the <i>Information</i> member to get the size of the buffer that the caller should allocate for this request.


## -remarks



The audio driver sends this request to obtain information about an enabled GUID_DEVINTERFACE_BLUETOOTH_HFP_SCO_HCIBYPASS device interface. The information does not change while the interface is enabled, but can change while the interface is disabled. Therefore the audio driver sends this request shortly after discovering an enabled device interface and uses the information to build an appropriate KSFILTER_DESCRIPTOR structure.

The audio driver sends this request once with an output buffer size of zero (0) in order to determine the required output buffer size. In this case, the request will complete with Status STATUS_BUFFER_TOO_SMALL and set the <i>Information</i> member to the required buffer size. The audio driver then allocates the necessary storage space and sends the request again. Typically an audio driver will store a pointer to this storage location in its device context for reference during later activity.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn302027">Bluetooth HFP DDI IOCTLs</a>



<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_ksnodetypes.md">IOCTL_BTHHFP_DEVICE_GET_KSNODETYPES</a>



<a href="..\bthhfpddi\ni-bthhfpddi-ioctl_bthhfp_device_get_containerid.md">IOCTL_BTHHFP_DEVICE_GET_CONTAINERID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_DEVICE_GET_DESCRIPTOR control code%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

