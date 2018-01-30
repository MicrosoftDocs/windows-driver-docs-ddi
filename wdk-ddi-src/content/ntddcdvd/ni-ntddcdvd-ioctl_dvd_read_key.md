---
UID: NI:ntddcdvd.IOCTL_DVD_READ_KEY
title: IOCTL_DVD_READ_KEY
author: windows-driver-content
description: Returns a copy-protection key of the specified type:\_challenge key, bus key, title key, read RPC key, set RPC key, or disk key.
old-location: storage\ioctl_dvd_read_key.htm
old-project: storage
ms.assetid: 42745dae-f472-4f64-8f16-9f4dec1e986a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_dvd_read_key, IOCTL_DVD_READ_KEY control code [Storage Devices], IOCTL_DVD_READ_KEY, ntddcdvd/IOCTL_DVD_READ_KEY, k307_6baca45d-504c-46b9-9724-f82132c2bead.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddcdvd.h
apiname:
-	IOCTL_DVD_READ_KEY
product: Windows
targetos: Windows
req.typenames: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
---

# IOCTL_DVD_READ_KEY IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Returns a copy-protection key of the specified type: challenge key, bus key, title key, read RPC key, set RPC key, or disk key. A challenge key or bus key is sent back to the device to complete the related step in a DVD authentication sequence. After the authentication sequence is completed, a title key is used to encrypt and decrypt user data transferred from a DVD disc and a disk key is used to encrypt and decrypt title key data. If the drive region has not been set previously (if it is still at factory default) and if the inserted media has a region, the device region will be set to the current media region.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a> structure that indicates the session ID of the DVD session and the type of key to return.  


### -input-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the buffer, which must be &gt;= the size of one of the following: DVD_CHALLENGE_KEY_LENGTH, DVD_BUS_KEY_LENGTH, DVD_TITLE_KEY_LENGTH, DVD_RPC_KEY_LENGTH, DVD_SET_RPC_KEY_LENGTH, or DVD_DISK_KEY_LENGTH.


### -output-buffer

The driver returns the DVD_COPY_PROTECT_KEY data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.


### -output-buffer-length

Length of a <a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a>.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-_dvd_copy_protect_key.md">DVD_COPY_PROTECT_KEY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DVD_READ_KEY control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

