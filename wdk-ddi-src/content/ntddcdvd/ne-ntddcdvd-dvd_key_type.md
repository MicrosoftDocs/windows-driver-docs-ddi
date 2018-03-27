---
UID: NE:ntddcdvd.DVD_KEY_TYPE
title: DVD_KEY_TYPE
author: windows-driver-content
description: The DVD_KEY_TYPE enumeration type is used in conjunction with the DVD_COPY_PROTECT_KEY structure to indicate a key to be read, to invalidate an authentication grant ID (AGID), and to request state information or region settings.
old-location: storage\dvd_key_type.htm
old-project: storage
ms.assetid: ec080043-a147-4002-8d0c-ed383182ec40
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DVD_KEY_TYPE, DVD_KEY_TYPE enumeration [Storage Devices], DvdAsf, DvdBusKey1, DvdBusKey2, DvdChallengeKey, DvdDiskKey, DvdGetRpcKey, DvdInvalidateAGID, DvdSetRpcKey, DvdTitleKey, ntddcdvd/DVD_KEY_TYPE, ntddcdvd/DvdAsf, ntddcdvd/DvdBusKey1, ntddcdvd/DvdBusKey2, ntddcdvd/DvdChallengeKey, ntddcdvd/DvdDiskKey, ntddcdvd/DvdGetRpcKey, ntddcdvd/DvdInvalidateAGID, ntddcdvd/DvdSetRpcKey, ntddcdvd/DvdTitleKey, storage.dvd_key_type, structs-DVD_922c1979-c628-441b-b8e9-5818f6ed737d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	ntddcdvd.h
api_name:
-	DVD_KEY_TYPE
product: Windows
targetos: Windows
req.typenames: DVD_KEY_TYPE
---

# DVD_KEY_TYPE enumeration


## -description


The DVD_KEY_TYPE enumeration type is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553718">DVD_COPY_PROTECT_KEY</a> structure to indicate a key to be read, to invalidate an authentication grant ID (AGID), and to request state information or region settings. 


## -enum-fields




### -field DvdChallengeKey

Gets a challenge key. This is used during the authentication key exchange process.


### -field DvdBusKey1

Gets the first bus key. 


### -field DvdBusKey2

Gets the second bus key. 


### -field DvdTitleKey

Gets a title key that is obfuscated by a bus key.


### -field DvdAsf

Gets the current state of the authentication success flag (ASF).


### -field DvdSetRpcKey

Sets the region playback contents (RPC) for the logical unit. 


### -field DvdGetRpcKey

Gets the region playback contents (RPC) for the logical unit. 


### -field DvdDiskKey

Gets the disc key. 


### -field DvdInvalidateAGID

Invalidates the specified authentication grant ID (AGID).


## -remarks



The driver for the DVD device uses the key type specified in this enumeration type to determine the key format in a report key command, as defined by the <i>SCSI Multimedia Commands - 3 (MMC-3) </i>specification. A report key command can either report key data for a specified key (challenge key, bus key, title key, RPC key, or disc key), or the state of the ASF flag. It can also invalidate an AGID. See the <i>MMC-3 </i>specification for further information. 

Drivers can issue a report key command to retrieve key data by means of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560425">IOCTL_DVD_READ_KEY</a> request. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553718">DVD_COPY_PROTECT_KEY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560425">IOCTL_DVD_READ_KEY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560427">IOCTL_DVD_SEND_KEY</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DVD_KEY_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

