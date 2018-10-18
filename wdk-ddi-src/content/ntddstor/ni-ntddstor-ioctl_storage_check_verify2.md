---
UID: NI:ntddstor.IOCTL_STORAGE_CHECK_VERIFY2
title: IOCTL_STORAGE_CHECK_VERIFY2
author: windows-driver-content
description: Determines whether the media has changed on a removable-media device - the caller has opened with FILE_READ_ATTRIBUTES.
old-location: storage\ioctl_storage_check_verify2.htm
tech.root: storage
ms.assetid: bac1e5ec-0e0c-4d7a-b260-2e73addd0abf
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_CHECK_VERIFY2, IOCTL_STORAGE_CHECK_VERIFY2 control, IOCTL_STORAGE_CHECK_VERIFY2 control code [Storage Devices], k307_81e9c9dd-6905-4d07-9da0-f54997bc8640.xml, ntddstor/IOCTL_STORAGE_CHECK_VERIFY2, storage.ioctl_storage_check_verify2
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_CHECK_VERIFY2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_CHECK_VERIFY2 IOCTL


## -description



Determines whether the media has changed on a removable-media device - the caller has opened with FILE_READ_ATTRIBUTES. Because no file system is mounted when a device is opened in this way, this request can be processed much more quickly than an IOCTL_STORAGE_CHECK_VERIFY request.




## -ioctlparameters




### -input-buffer

Input is identical to the input for <a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -input-buffer-length

Input length is identical to input length for <a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -output-buffer

Output is identical to the output for <a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -output-buffer-length

Output length is identical to output length for <a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -in-out-buffer








### -inout-buffer-length








### -status-block

I/O status is identical to the I/O status for <a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>
 

 

