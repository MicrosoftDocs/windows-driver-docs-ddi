---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_ACTIVATE
title: IOCTL_EHSTOR_BANDMGMT_ACTIVATE
author: windows-driver-content
description: This IOCTL_EHSTOR_BANDMGMT_ACTIVATE request is sent to activate the security features and band management on a storage device. The request includes activation options and the authentication key.
old-location: storage\ioctl_ehstor_bandmgmt_activate.htm
old-project: storage
ms.assetid: 10C3077A-1A6A-4AA1-BC9B-829353A8A895
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_EHSTOR_BANDMGMT_ACTIVATE, IOCTL_EHSTOR_BANDMGMT_ACTIVATE control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_ACTIVATE, storage.ioctl_ehstor_bandmgmt_activate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with  Windows 8.
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
-	EhStorBandMgmt.h
api_name:
-	IOCTL_EHSTOR_BANDMGMT_ACTIVATE
product:
- Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# IOCTL_EHSTOR_BANDMGMT_ACTIVATE IOCTL


## -description


This <b>IOCTL_EHSTOR_BANDMGMT_ACTIVATE</b> request is sent to activate the security features and band management on a storage device. The request includes activation options and the authentication key.


## -ioctlparameters




### -input-buffer

The input buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an  <b>ACTIVATE_REVERT_PARAMETERS</b>  structure. <b>ACTIVATE_REVERT_PARAMETERS</b> is declared in <i>ehstorbandmgmt.h</i> as the following.

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



#### -AuthKeyOffset

The offset from the beginning of the system buffer to the location of an <b>AUTH_KEY</b> structure.


#### -Flags

A bitmask of activation flags. This is a bitwise OR value of the following.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>ACTIVATE_DISABLE_SID</td>
<td>SID authority will be disabled after activation.</td>
</tr>
<tr>
<td>ACTIVATE_IGNORE_POLICY</td>
<td>Activate will ignore the global policy for security activation. </td>
</tr>
</table>
 


#### -Key

A variable length byte array that contains the key data.


#### -KeySize

The size of the key, in bytes, of the key data at <b>Key</b>. If <b>KeySize</b> is set to 0, a default key is used.


#### -StructSize

The size of the structure. This is set to <b>sizeof</b>(ACTIVATE_REVERT_PARAMETERS).


### -input-buffer-length

The length of an  <b>ACTIVATE_REVERT_PARAMETERS</b>  structure.


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
<td>Security features on the storage device were activated.</td>
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
<td>The authentication key is invalid. Activation is denied.</td>
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
<td>The storage device is already activated.</td>
</tr>
<tr>
<td>STATUS_NOT_SUPPORTED</td>
<td>Security features on the device were not activated because of a Group Policy setting.</td>
</tr>
</table>
 


## -remarks



If STATUS_SUCCESS is returned from this request, a driver or application can then send an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451390">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a> request to retrieve the enabled band management capabilities of the device.

Before a successful return from <b>IOCTL_EHSTOR_BANDMGMT_ACTIVATE</b>, the device is not activated. Until the device is activated, the only band management IOCTL that will   return successfully is <a href="https://msdn.microsoft.com/library/windows/hardware/hh451390">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>. After activation, the remaining band management IOCTLs are available.

Activation of Enhanced Storage devices is controlled by the Group Policy settings of the system.  The registry value at <i>HKLM\Software\Policies\Microsoft\Windows\EnhancedStorageDevices\TCGSecurityActivationDisabled</i> determines whether security activation is 
enabled. A REG_DWORD value of 0 allows security activation on the storage device. Otherwise, a value of 1 disables security activation and the <b>IOCTL_EHSTOR_BANDMGMT_ACTIVATE</b> request will return with <b>STATUS_NOT_SUPPORTED.</b>




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451390">IOCTL_EHSTOR_BANDMGMT_QUERY_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451392">IOCTL_EHSTOR_BANDMGMT_REVERT</a>
 

 

