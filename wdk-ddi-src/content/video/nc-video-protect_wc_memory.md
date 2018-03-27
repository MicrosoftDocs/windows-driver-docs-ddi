---
UID: NC:video.PROTECT_WC_MEMORY
title: PROTECT_WC_MEMORY
author: windows-driver-content
description: The VideoPortProtectWCMemory callback routine protects Write Combined (WC) video memory from being accessed by the CPU.
old-location: display\videoportprotectwcmemory.htm
old-project: display
ms.assetid: 0cee4f4d-4d9c-44be-94ad-459000f2adb1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PROTECT_WC_MEMORY, VideoPortProtectWCMemory, VideoPortProtectWCMemory callback function [Display Devices], VideoPort_Functions_5aead504-6c27-4b86-95e0-b4ec1b2b3e7d.xml, display.videoportprotectwcmemory, video/VideoPortProtectWCMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	VideoPortProtectWCMemory
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---

# PROTECT_WC_MEMORY callback


## -description


The <i>VideoPortProtectWCMemory</i> callback routine protects Write Combined (WC) video memory from being accessed by the CPU.


## -parameters




### -param Context [in]

Pointer to a caller-determined context parameter to be passed to the <i>CallbackRoutine</i>. It typically points to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> buffer.


### -param HwDeviceExtension [in]

Pointer to the miniport driver's hardware device extension.


## -returns



<i>VideoPortProtectWCMemory</i> returns NO_ERROR if it successfully protects Write Combined video memory; otherwise, it returns an error status of ERROR_INVALID_FUNCTION or ERROR_NOT_ENOUGH_MEMORY.




## -remarks



After <i>VideoPortProtectWCMemory</i> is called, the CPU cannot write to Write Combined (WC) memory until the <a href="https://msdn.microsoft.com/8fa0be0c-04ce-41ab-93dd-6dc9e8daa356">VideoPortRestoreWCMemory</a> callback routine is called.

When WC memory protection is no longer required, the display miniport driver should call <a href="https://msdn.microsoft.com/8fa0be0c-04ce-41ab-93dd-6dc9e8daa356">VideoPortRestoreWCMemory</a> to restore CPU access to WC memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/8fa0be0c-04ce-41ab-93dd-6dc9e8daa356">VideoPortRestoreWCMemory</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PROTECT_WC_MEMORY callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

