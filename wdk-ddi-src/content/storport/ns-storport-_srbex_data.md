---
UID: NS:storport._SRBEX_DATA
title: _SRBEX_DATA
author: windows-driver-content
description: The SRBEX_DATA structure is the generalized format for containing extended SRB data.
old-location: storage\srbex_data.htm
old-project: storage
ms.assetid: 15FB9877-6339-484B-83D5-6AD44EEE1D6E
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SRBEX_DATA, *PSRBEX_DATA, SRBEX_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h, Srb.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SRBEX_DATA
req.alt-loc: Storport.h
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
req.typenames: *PSRBEX_DATA, SRBEX_DATA
req.product: Windows 10 or later.
---

# _SRBEX_DATA structure



## -description
The <b>SRBEX_DATA</b> structure is the generalized format for containing extended SRB data.



## -syntax

````
typedef struct _SRBEX_DATA {
  SRBEXDATATYPE Type;
  ULONG         Length;
  UCHAR         Data[ANYSIZE_ARRAY];
} SRBEX_DATA, *PSRBEX_DATA;
````


## -struct-fields

### -field Type

Data type indicator for the extended SRB data structure. The possible values for <b>Type</b> are one of the following.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field SrbExDataTypeUnknown

</td>
<td width="60%">
The SRB extended data type is unknown.

</td>
</tr>
<tr>

### -field SrbExDataTypeBidirectional

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_bidirectional.md">SRBEX_DATA_BIDIRECTIONAL</a> structure.

</td>
</tr>
<tr>

### -field SrbExDataTypeScsiCdb16

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a> structure.

</td>
</tr>
<tr>

### -field SrbExDataTypeScsiCdb32

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a> structure.

</td>
</tr>
<tr>

### -field SrbExDataTypeScsiCdbVar

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_scsi_cdb_var.md">SRBEX_DATA_SCSI_CDB_VAR</a> structure.

</td>
</tr>
<tr>

### -field SrbExDataTypeWmi

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_wmi.md">SRBEX_DATA_WMI</a> structure.

</td>
</tr>
<tr>

### -field SrbExDataTypePower

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_power.md">SRBEX_DATA_POWER</a> structure.

</td>
</tr>
<tr>

### -field SrbExDataTypePnp

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_pnp.md">SRBEX_DATA_PNP</a> structure.

</td>
</tr>
<tr>

### -field SrbExDataTypeIoInfo

</td>
<td width="60%">
The SRB extended data is formatted as an <a href="..\srb\ns-srb-_srbex_data_io_info.md">SRBEX_DATA_IO_INFO</a> structure.

</td>
</tr>
</table>
 


### -field Length

Length of the SRB data, in bytes, present  in the <b>Data</b> member.


### -field Data

The extended SRB data block contents.


## -remarks
The SRB extended data is present when the <b>SrbExDataOffset</b> array in the <a href="..\srb\ns-srb-_storage_request_block.md">STORAGE_REQUEST_BLOCK</a> structure contains valid offset locations.  A storage driver initially references a memory offset location contained in <b>SrbExDataOffset</b> as an <b>SRBEX_DATA</b> structure. A pointer to the data block is then cast to the appropriate structure type based on the data type value in the <b>Type</b> member.

The following example code fragment shows how to access the extended data for the an SRB function of SRB_FUNCTION_PNP.


## -see-also
<dl>
<dt>
<a href="..\srb\ns-srb-_srbex_data_bidirectional.md">SRBEX_DATA_BIDIRECTIONAL</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_srbex_data_io_info.md">SRBEX_DATA_IO_INFO</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_srbex_data_pnp.md">SRBEX_DATA_PNP</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_srbex_data_power.md">SRBEX_DATA_POWER</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_srbex_data_scsi_cdb16.md">SRBEX_DATA_SCSI_CDB16</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_srbex_data_scsi_cdb32.md">SRBEX_DATA_SCSI_CDB32</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_srbex_data_scsi_cdb_var.md">SRBEX_DATA_SCSI_CDB_VAR</a>
</dt>
<dt>
<a href="..\srb\ns-srb-_srbex_data_wmi.md">SRBEX_DATA_WMI</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SRBEX_DATA structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

