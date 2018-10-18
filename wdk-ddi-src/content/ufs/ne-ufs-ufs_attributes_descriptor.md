---
UID: NE:ufs.UFS_ATTRIBUTES_DESCRIPTOR
title: UFS_ATTRIBUTES_DESCRIPTOR
author: windows-driver-content
description: UFS_ATTRIBUTES_DESCRIPTOR describes the different types of attributes used by Universal Flash Storage (UFS) descriptors.
old-location: storage\ufs_attributes_descriptor.htm
tech.root: storage
ms.assetid: 695D8FE9-FADB-488F-A5F7-7715EAD48DD6
ms.date: 3/29/2018
ms.keywords: UFS_ATTRIBUTES_DESCRIPTOR, UFS_ATTRIBUTES_DESCRIPTOR enumeration [Storage Devices], UFS_Obsolete, UFS_Reserved01, UFS_Reserved02, UFS_Reserved03, UFS_bActiveICCLevel, UFS_bBackgroundOpStatus, UFS_bBootLunEn, UFS_bConfigDescrLock, UFS_bCurrentPowerMode, UFS_bDeviceFFUStatus, UFS_bMaxDataInSize, UFS_bMaxDataOutSize, UFS_bMaxNumOfRTT, UFS_bOutOfOrderDataEn, UFS_bPSAState, UFS_bPurgeStatus, UFS_bRefClkFreq, UFS_dDynCapNeeded, UFS_dPSADataSize, UFS_dSecondsPassed, UFS_wContextConf, UFS_wExceptionEventControl, UFS_wExceptionEventStatus, storage.ufs_attributes_descriptor, ufs/UFS_ATTRIBUTES_DESCRIPTOR, ufs/UFS_Obsolete, ufs/UFS_Reserved01, ufs/UFS_Reserved02, ufs/UFS_Reserved03, ufs/UFS_bActiveICCLevel, ufs/UFS_bBackgroundOpStatus, ufs/UFS_bBootLunEn, ufs/UFS_bConfigDescrLock, ufs/UFS_bCurrentPowerMode, ufs/UFS_bDeviceFFUStatus, ufs/UFS_bMaxDataInSize, ufs/UFS_bMaxDataOutSize, ufs/UFS_bMaxNumOfRTT, ufs/UFS_bOutOfOrderDataEn, ufs/UFS_bPSAState, ufs/UFS_bPurgeStatus, ufs/UFS_bRefClkFreq, ufs/UFS_dDynCapNeeded, ufs/UFS_dPSADataSize, ufs/UFS_dSecondsPassed, ufs/UFS_wContextConf, ufs/UFS_wExceptionEventControl, ufs/UFS_wExceptionEventStatus
ms.topic: enum
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
-	Ufs.h
api_name:
-	UFS_ATTRIBUTES_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: UFS_ATTRIBUTES_DESCRIPTOR
---

# UFS_ATTRIBUTES_DESCRIPTOR enumeration


## -description


<b>UFS_ATTRIBUTES_DESCRIPTOR</b> describes the different types of attributes used by Universal Flash Storage (UFS) descriptors.


## -enum-fields




### -field UFS_bBootLunEn

Indicates if the Boot Logical Unit Number(LUN) is enabled.


### -field UFS_Reserved01

Reserved for future use.


### -field UFS_bCurrentPowerMode

Indicates the current power mode. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Idle power mode.</td>
</tr>
<tr>
<td>0x10</td>
<td>Pre-Active power mode.</td>
</tr>
<tr>
<td>0x11</td>
<td>Active power mode.</td>
</tr>
<tr>
<td>0x20</td>
<td>Pre-Sleep power mode.</td>
</tr>
<tr>
<td>0x22</td>
<td>Universal Flash Storage (UFS)-Sleep power mode.</td>
</tr>
<tr>
<td>0x30</td>
<td>40% to 50% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x33</td>
<td>50% to 60% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
 


### -field UFS_bActiveICCLevel

Specifies the maximum
current consumption allowed during
Active Mode. Value ranges from 0x00 to 0x0F.


### -field UFS_bOutOfOrderDataEn

Specifies if out-of-order data transfer is
enabled


### -field UFS_bBackgroundOpStatus

Specifies if the device has a need for background operations. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Device requires no background operations.</td>
</tr>
<tr>
<td>0x01</td>
<td>Device has a non-critical need of background operations.</td>
</tr>
<tr>
<td>0x02</td>
<td>Device has a performance impacted-based need of background operations.</td>
</tr>
<tr>
<td>0x03</td>
<td>Device has a critical need of background operations. </td>
</tr>
</table>
 


### -field UFS_bPurgeStatus

Specifies the current purge operation's status.


### -field UFS_bMaxDataInSize

Specifies the maximum data size in a DATA IN UFS Protocol Information Units (UPIU). This parameter can be written by the
host only when all logical unit task queues are
empty.


### -field UFS_bMaxDataOutSize

Specifies the maximum data-out size. This parameter can be written by the
host only when all logical unit task queues are
empty.


### -field UFS_dDynCapNeeded

Specifies the dynamic capacity need.


### -field UFS_bRefClkFreq

Specifies the reference clock frequency value.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>19.2 MHz</td>
</tr>
<tr>
<td>0x01</td>
<td>26 MHz</td>
</tr>
<tr>
<td>0x02</td>
<td>38.4 MHz</td>
</tr>
<tr>
<td>0x03</td>
<td>52 MHz</td>
</tr>
</table>
 


### -field UFS_bConfigDescrLock

Specifies if the configuration descriptor is locked.


### -field UFS_bMaxNumOfRTT

Defines the current maximum number of outstanding READY TO TRANSFER UPIU’s (RTT's) that are
allowed. This value can be set by the host.


### -field UFS_wExceptionEventControl

Specifies the Exception Event Controller. <b>UFS_wExceptionEventControl</b> enables the setting of the
<b>EVENT_ALERT</b> bit in the Device
Information field, which is contained in
the RESPONSE UPIU.


### -field UFS_wExceptionEventStatus

Specifies a bitmap of each exception event status.A bit will be set only if the
relevant event has occurred
(regardless of the
<b>UFS_wExceptionEventControl</b> status). Contains the following bits:

<table>
<tr>
<th>Bit</th>
<th>Value</th>
</tr>
<tr>
<td>0</td>
<td>DYNCAP_NEEDED</td>
</tr>
<tr>
<td>1</td>
<td>SYSPOOL_EXHAUSTED</td>
</tr>
<tr>
<td>2</td>
<td>URGENT_BKOPS</td>
</tr>
<tr>
<td>3 to 15</td>
<td>Reserved.</td>
</tr>
</table>
 


### -field UFS_dSecondsPassed

Specifies the time passed in seconds.


### -field UFS_wContextConf

Specifies the context attribute.


### -field UFS_Obsolete

Obselete


### -field UFS_Reserved02

Reserved for future use.


### -field UFS_Reserved03

Reserved for future use.


### -field UFS_bDeviceFFUStatus

Specifies the Device Field Firmware Update (FFU) status.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>No information on the FFU status.</td>
</tr>
<tr>
<td>0x01</td>
<td>Successful microcode update.</td>
</tr>
<tr>
<td>0x02</td>
<td>Microcode corruption error.</td>
</tr>
<tr>
<td>0x03</td>
<td>Internal error.</td>
</tr>
<tr>
<td>0x04</td>
<td>Microcode version mismatch.</td>
</tr>
<tr>
<td>0x05 to 0xFE </td>
<td>Reserved.</td>
</tr>
<tr>
<td>0xFF</td>
<td>General Error.</td>
</tr>
</table>
 


### -field UFS_bPSAState

Specifies the current Product State Awareness (PSA) State.

<table>
<tr>
<th>Value</th>
<th>State</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Off</td>
<td>PSA feature is off.</td>
</tr>
<tr>
<td>0x01</td>
<td>Pre-solder</td>
<td>PSA feature is on and the device is in a pre-soldering state.</td>
</tr>
<tr>
<td>0x02</td>
<td>Loading Complete</td>
<td>The PSA feature
is on. The host will set to this
value after the host finished
writing data during pre-soldering
state.</td>
</tr>
<tr>
<td>0x03</td>
<td>Soldered</td>
<td>PSA feature is no
longer available. Set by the
Device to indicate it is in a post-soldering state. This attribute
is locked after it is in
‘Soldered’ state.</td>
</tr>
</table>
 


### -field UFS_dPSADataSize

Specifies the amount of data that the host plans
to load to all logical units with
<b>bPSASensitive</b> set to 1.


## -remarks



<b>UFS_bCurrentPowerMode</b> is the only attribute the device is required to return in any power mode. If the device
is not in Active power mode or Idle power mode, a <b>QUERY REQUEST UPIU</b> to access descriptors, flags, or attributes other than <b>bCurrentPowerMode</b> may fail.

<b>UFS_bDeviceFFUStatu</b>s value is kept after power cycle, hardware reset or any other type of reset. This attribute may change value when a
microcode activation event occurs.

<b>UFS_bMaxDataInSize</b> is equal to <b>bMaxInBufferSize</b> when a UFS device is shipped. 




## -see-also




<a href="https://msdn.microsoft.com/B65A2268-6959-4630-97DA-C0CFD37D9174">UFS_CONFIG_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/CD1F59DA-3D84-422B-A862-8F4C5E1AA515">UFS_DEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/6B085DBB-2AAA-4170-A2B1-EA4D2C207A24">UFS_DEVICE_HEALTH_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/DD3AEB66-E36B-4F18-AFEC-D344132D4B8C">UFS_GEOMETRY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/6C6EAA96-40E9-467F-903B-AE44CE5B77CF">UFS_INTERCONNECT_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/FCF9DCD1-2C04-47E3-97C5-7ACC28B28C6C">UFS_POWER_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/19A066BD-1099-475C-BF81-F1BE7C7778E5">UFS_RPMB_UNIT_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/1F32DA95-6801-4C48-B3C4-A47C3E1C678B">UFS_STRING_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/09CBAD0A-CBDC-464E-908C-BF142D515969">UFS_UNIT_CONFIG_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/5D76C266-875A-40AC-9B26-F17978971783">UFS_UNIT_DESCRIPTOR</a>
 

 

