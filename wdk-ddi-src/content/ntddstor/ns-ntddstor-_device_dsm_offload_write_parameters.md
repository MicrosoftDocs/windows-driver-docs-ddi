---
UID: NS:ntddstor._DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
title: "_DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS"
description: The DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure specifies the parameters for an offload write action related to the data-set attributes for a device.
old-location: storage\device_dsm_offload_write_parameters.htm
tech.root: storage
ms.assetid: B0E9DABD-0D5B-4F5D-8CB0-470AC126F9C0
ms.date: 03/29/2018
ms.keywords: "*PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure [Storage Devices], PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure pointer [Storage Devices], _DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, ntddstor/DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, ntddstor/PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, storage.device_dsm_offload_write_parameters"
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
-	ntddstor.h
api_name:
-	DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS, *PDEVICE_DSM_OFFLOAD_WRITE_PARAMETERS
---

# _DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS structure


## -description


The <b>DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</b> structure specifies the parameters for an offload write action related to the data-set attributes for a device. 

This parameter structure is used in an offload write  action for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.  The <b>Action</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> structure is set to <b>DeviceDsmAction_OffloadWrite</b>, and <b>ParameterBlockOffset</b> indicates the location of <b>DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</b>.


## -struct-fields




### -field Flags

Not used.


### -field Reserved

Reserved.


### -field TokenOffset

The offset, in bytes, within the data block specified by <b>Token</b> to begin writing from.


### -field Token

The unique identifier of the data block to write from.


## -remarks



The <b>ParameterBlockOffset</b> and <b>ParameterBlockLength</b> members  of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> are set to the location and length of the  <b>DEVICE_DSM_OFFLOAD_WRITE_PARAMETERS</b> structure in the system buffer of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a> request.

The <b>DataSetRangesOffset</b> and <b>DataSetRangesLength</b> members of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a> specify the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552523">DEVICE_DATA_SET_RANGE</a> structures for the extents of the offload write.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552527">DEVICE_MANAGE_DATA_SET_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560573">IOCTL_STORAGE_MANAGE_DATA_SET_ATTRIBUTES</a>
 

 

