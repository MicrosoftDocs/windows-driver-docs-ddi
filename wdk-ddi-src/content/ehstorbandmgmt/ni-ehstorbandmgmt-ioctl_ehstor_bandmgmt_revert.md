---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_REVERT
title: IOCTL_EHSTOR_BANDMGMT_REVERT
author: windows-driver-content
description: This IOCTL_EHSTOR_BANDMGMT_REVERT request is sent to deactivate the security features and band management on a storage device. The request includes revert options and the authentication key.
old-location: storage\ioctl_ehstor_bandmgmt_revert.htm
old-project: storage
ms.assetid: 981655A8-B6DC-4720-8D2E-B42AA0859FB2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_REVERT, IOCTL_EHSTOR_BANDMGMT_REVERT control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_REVERT, storage.ioctl_ehstor_bandmgmt_revert
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
-	EhStorBandMgmt.h
apiname:
-	IOCTL_EHSTOR_BANDMGMT_REVERT
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_REVERT IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


This <b>IOCTL_EHSTOR_BANDMGMT_REVERT</b> request is sent to deactivate the security features and band management on a storage device. The request includes revert options and the authentication key.


## -ioctlparameters




### -input-buffer

The input buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <b> ACTIVATE_REVERT_PARAMETERS</b>  structure. <b>ACTIVATE_REVERT_PARAMETERS</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _ACTIVATE_REVERT_PARAMETERS
{
    ULONG           StructSize;
    ULONG           Flags;
    ULONG           AuthKeyOffset;
} ACTIVATE_REVERT_PARAMETERS;</pre>
</td>
</tr>
</table></span></div>


Following <b>ACTIVATE_REVERT_PARAMETERS</b> in the system buffer is an <b>AUTH_KEY</b> structure. This holds the key data bytes for the authentication key. <b>AUTH_KEY</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _AUTH_KEY
{
    ULONG   KeySize;
    UCHAR   Key[ANYSIZE_ARRAY];
} AUTH_KEY;</pre>
</td>
</tr>
</table></span></div>



#### -StructSize

The size of the structure. This is set to <b>sizeof</b>(ACTIVATE_REVERT_PARAMETERS).


#### -Flags

A bitmask of deactivation flags. This is a bitwise OR value of the following.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>REVERT_PSID_AUTHKEY</td>
<td>The authentication key at <b>AuthKeyOffset</b> is a PSID key.</td>
</tr>
</table>
 


#### -AuthKeyOffset

The offset from the beginning of the system buffer to the location of an <b>AUTH_KEY</b> structure.


#### -KeySize

The size of the key, in bytes, of the key data at <b>Key</b>. If <b>KeySize</b> is set to 0, a default key is used.


#### -Key

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

One of the following values can be returned in the <b>Status</b> field.

<table>
<tr>
<th>Status Value</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_SUCCESS</td>
<td>Security features on the storage device were deactivated.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_REQUEST</td>
<td>The storage device does not support band management.</td>
</tr>
<tr>
<td>STATUS_INVALID_BUFFER_SIZE</td>
<td>The input buffer size is invalid.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>Information in the input buffer is invalid.</td>
</tr>
<tr>
<td>STATUS_ACCESS_DENIED</td>
<td>The authentication key is invalid. Deactivation is denied.</td>
</tr>
<tr>
<td>STATUS_DEVICE_CONFIGURATION_ERROR</td>
<td>The system cannot configure the device in a supported mode.</td>
</tr>
<tr>
<td>STATUS_IO_DEVICE_ERROR</td>
<td>Communication failed. The storage device might be incompatible with security protocols. </td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_STATE</td>
<td>The storage device is not activated.</td>
</tr>
</table>
 


## -remarks



On successful return from an  <b>IOCTL_EHSTOR_BANDMGMT_REVERT</b> request, the storage device will return to an inactive security state and all band management IOCTLs, except for <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a> and <a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate.md">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a>, become unavailable.




## -see-also

<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_query_capabilities.md">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>



<a href="..\ehstorbandmgmt\ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_activate.md">IOCTL_EHSTOR_BANDMGMT_ACTIVATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_EHSTOR_BANDMGMT_REVERT control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

