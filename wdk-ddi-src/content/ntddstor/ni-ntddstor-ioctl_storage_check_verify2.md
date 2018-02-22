---
UID: NI:ntddstor.IOCTL_STORAGE_CHECK_VERIFY2
title: IOCTL_STORAGE_CHECK_VERIFY2
author: windows-driver-content
description: Determines whether the media has changed on a removable-media device - the caller has opened with FILE_READ_ATTRIBUTES.
old-location: storage\ioctl_storage_check_verify2.htm
old-project: storage
ms.assetid: bac1e5ec-0e0c-4d7a-b260-2e73addd0abf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_storage_check_verify2, IOCTL_STORAGE_CHECK_VERIFY2 control code [Storage Devices], IOCTL_STORAGE_CHECK_VERIFY2, ntddstor/IOCTL_STORAGE_CHECK_VERIFY2, k307_81e9c9dd-6905-4d07-9da0-f54997bc8640.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	IOCTL_STORAGE_CHECK_VERIFY2
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONE_CONDITION, STORAGE_ZONE_CONDITION"
---

# IOCTL_STORAGE_CHECK_VERIFY2 IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Determines whether the media has changed on a removable-media device - the caller has opened with FILE_READ_ATTRIBUTES. Because no file system is mounted when a device is opened in this way, this request can be processed much more quickly than an IOCTL_STORAGE_CHECK_VERIFY request.




## -ioctlparameters




### -input-buffer

Input is identical to the input for <a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify.md">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -input-buffer-length

Input length is identical to input length for <a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify.md">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -output-buffer

Output is identical to the output for <a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify.md">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -output-buffer-length

Output length is identical to output length for <a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify.md">IOCTL_STORAGE_CHECK_VERIFY</a>. 


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

I/O status is identical to the I/O status for <a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify.md">IOCTL_STORAGE_CHECK_VERIFY</a>. 


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_check_verify.md">IOCTL_STORAGE_CHECK_VERIFY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_CHECK_VERIFY2 control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

