---
UID: NS:ntddstor._DEVICE_MANAGE_DATA_SET_ATTRIBUTES
title: "_DEVICE_MANAGE_DATA_SET_ATTRIBUTES"
author: windows-driver-content
description: The DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure specifies a management action for the data-set attributes for a device.
old-location: storage\device_manage_data_set_attributes.htm
old-project: storage
ms.assetid: be0bfcef-09df-4259-a034-0d51db9819ce
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES, ,, A, B, C, D, DEVICE_DSM_FLAG_ENTIRE_DATA_SET_RANGE, DEVICE_MANAGE_DATA_SET_ATTRIBUTES, DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure [Storage Devices], DeviceDsmActionFlag_NonDestructive, E, G, I, M, N, P, PDEVICE_MANAGE_DATA_SET_ATTRIBUTES, PDEVICE_MANAGE_DATA_SET_ATTRIBUTES structure pointer [Storage Devices], R, S, T, U, V, _, _DEVICE_MANAGE_DATA_SET_ATTRIBUTES, ntddstor/DEVICE_MANAGE_DATA_SET_ATTRIBUTES, ntddstor/PDEVICE_MANAGE_DATA_SET_ATTRIBUTES, storage.device_manage_data_set_attributes, structs-general_f8d2d431-7187-4532-ac05-69868909fc66.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	ntddstor.h
apiname:
-	DEVICE_MANAGE_DATA_SET_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: DEVICE_MANAGE_DATA_SET_ATTRIBUTES, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES
---

# _DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure


## -description


The 
    <b>DEVICE_MANAGE_DATA_SET_ATTRIBUTES</b> 
    structure specifies a management action for the data-set attributes for a device.

The management action is specified in the 
    <b>DEVICE_MANAGE_DATA_SET_ATTRIBUTES</b> 
    structure that is contained in the system buffer of an 
    <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> 
    request.


## -syntax


````
typedef struct _DEVICE_MANAGE_DATA_SET_ATTRIBUTES {
  ULONG                             Size;
  DEVICE_DATA_MANAGEMENT_SET_ACTION Action;
  ULONG                             Flags;
  ULONG                             ParameterBlockOffset;
  ULONG                             ParameterBlockLength;
  ULONG                             DataSetRangesOffset;
  ULONG                             DataSetRangesLength;
} DEVICE_MANAGE_DATA_SET_ATTRIBUTES, *PDEVICE_MANAGE_DATA_SET_ATTRIBUTES;
````


## -struct-fields




### -field Size

Contains the size of the structure 
      <b>DEVICE_MANAGE_DATA_SET_ATTRIBUTES</b>. 
      The value of this member will change as members are added to the structure.


### -field Action

The action to be performed as specified by a 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a> 
       enumeration value.

Starting with Windows 7, this value can be a bitwise OR of one or more of the following flags:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DeviceDsmActionFlag_NonDestructive"></a><a id="devicedsmactionflag_nondestructive"></a><a id="DEVICEDSMACTIONFLAG_NONDESTRUCTIVE"></a><dl>
<dt><b><b>DeviceDsmActionFlag_NonDestructive</b></b></dt>
</dl>
</td>
<td width="60%">
The specified action is non-destructive. If this flag is set, the driver can safely forward the 
         <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> 
         request to the next lower driver in the stack even if the driver does not handle the specified action.

<div class="alert"><b>Note</b>  Before it forwards the 
         <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> 
         request, the driver should still perform the normal processing of the data set ranges block that is specified 
         by the <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> 
         members.</div>
<div> </div>
</td>
</tr>
</table>
 


### -field Flags

These flags are global to all control actions. The following flags can be set in the 
       <b>Flags</b> member:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DEVICE_DSM_FLAG_ENTIRE_DATA_SET_RANGE"></a><a id="device_dsm_flag_entire_data_set_range"></a><dl>
<dt><b><b>DEVICE_DSM_FLAG_ENTIRE_DATA_SET_RANGE</b></b></dt>
</dl>
</td>
<td width="60%">
Specifies that the control action is specified for the entire block of data set ranges. If this flag is 
         set, the <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> 
         members must be set to zero.

</td>
</tr>
</table>
 


### -field ParameterBlockOffset

Specifies the start of the parameter block within the system buffer of the 
       <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> 
       request. The format of the parameter block depends on the value of the <b>Action</b> 
       member. For more information, see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>.

<div class="alert"><b>Note</b>  The offset of the parameter block must be aligned on the address boundary of the corresponding parameter 
      structure.</div>
<div> </div>
If set to zero, then the parameter block does not exist.


### -field ParameterBlockLength

Specifies the length, in bytes, of the parameter block within the payload of the 
       <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> 
       request.

If set to zero, then the parameter block does not exist.


### -field DataSetRangesOffset

Specifies the start of the block of data set ranges within the system buffer of the 
       <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> 
       request. This block consists of one or more contiguous entries that are formatted as 
       <a href="..\ntddstor\ns-ntddstor-_device_data_set_range.md">DEVICE_DATA_SET_RANGE</a> structures.

<div class="alert"><b>Note</b>  The offset of the data set range block must be aligned on the address boundary of the 
       <a href="..\ntddstor\ns-ntddstor-_device_data_set_range.md">DEVICE_DATA_SET_RANGE</a> structure.</div>
<div> </div>
If set to zero, then the block of data set ranges does not exist. 


### -field DataSetRangesLength

Specifies the length, in bytes, of the block of data set ranges within the payload of the 
       <a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> 
       request.

If set to zero, then the block of data set ranges does not exist.


## -remarks



The block of data set ranges is specified by the <b>DataSetRangesOffset</b> and 
     <b>DataSetRangesLength</b> members. If this block exists, it contains contiguous 
     <a href="..\ntddstor\ns-ntddstor-_device_data_set_range.md">DEVICE_DATA_SET_RANGE</a> structures. The total 
     size of the buffer should be at least:

<code>sizeof(DEVICE_MANAGE_DATA_SET_ATTRIBUTES) + ParameterBlockLength + DataSetRangesLength</code>




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552520">DEVICE_DATA_MANAGEMENT_SET_ACTION</a>



<a href="..\ntddstor\ni-ntddstor-ioctl_storage_manage_data_set_attributes.md">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DEVICE_MANAGE_DATA_SET_ATTRIBUTES structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

