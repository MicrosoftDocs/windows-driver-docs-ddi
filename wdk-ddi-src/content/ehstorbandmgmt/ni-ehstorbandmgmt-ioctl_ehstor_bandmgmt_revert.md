---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_REVERT
title: IOCTL_EHSTOR_BANDMGMT_REVERT
author: windows-driver-content
description: This IOCTL_EHSTOR_BANDMGMT_REVERT request is sent to deactivate the security features and band management on a storage device. The request includes revert options and the authentication key.
old-location: storage\ioctl_ehstor_bandmgmt_revert.htm
old-project: storage
ms.assetid: 981655A8-B6DC-4720-8D2E-B42AA0859FB2
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DXVA_VideoSample32, DXVA_VideoSample32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_EHSTOR_BANDMGMT_REVERT
req.alt-loc: EhStorBandMgmt.h
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
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_REVERT IOCTL



## -description
This <b>IOCTL_EHSTOR_BANDMGMT_REVERT</b> request is sent to deactivate the security features and band management on a storage device. The request includes revert options and the authentication key.



## -syntax

````
typedef struct _ACTIVATE_REVERT_PARAMETERS
{
    ULONG           StructSize;
    ULONG           Flags;
    ULONG           AuthKeyOffset;
} ACTIVATE_REVERT_PARAMETERS;
````


## -ioctlparameters

### -input-buffer
The input buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <b> ACTIVATE_REVERT_PARAMETERS</b>  structure. <b>ACTIVATE_REVERT_PARAMETERS</b> is declared in <i>ehstorbandmgmt.h</i> as the following.



The size of the structure. This is set to <b>sizeof</b>(ACTIVATE_REVERT_PARAMETERS).

A bitmask of deactivation flags. This is a bitwise OR value of the following.

 

The offset from the beginning of the system buffer to the location of an <b>AUTH_KEY</b> structure.

Following <b>ACTIVATE_REVERT_PARAMETERS</b> in the system buffer is an <b>AUTH_KEY</b> structure. This holds the key data bytes for the authentication key. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.



The size of the key, in bytes, of the key data at <b>Key</b>. If <b>KeySize</b> is set to 0, a default key is used.

A variable length byte array that contains the key data.


### -input-buffer-length
The length of an <b> ACTIVATE_REVERT_PARAMETERS</b> structure.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
One of the following values can be returned in the <b>Status</b> field.

 


## -remarks
On successful return from an  <b>IOCTL_EHSTOR_BANDMGMT_REVERT</b> request, the storage device will return to an inactive security state and all band management IOCTLs, except for <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a> and <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate.md">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a>, become unavailable.


## -see-also
<dl>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate.md">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a>
</dt>
<dt>
<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_REVERT control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

