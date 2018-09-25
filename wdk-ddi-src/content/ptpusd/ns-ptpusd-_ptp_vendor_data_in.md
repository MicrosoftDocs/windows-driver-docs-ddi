---
UID: NS:ptpusd._PTP_VENDOR_DATA_IN
title: "_PTP_VENDOR_DATA_IN"
author: windows-driver-content
description: The PTP_VENDOR_DATA_IN structure contains information about an arbitrary command that an application issues to the device.
old-location: image\ptp_vendor_data_in.htm
tech.root: image
ms.assetid: 896209d0-d545-495b-b743-98c0b9d976ff
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: "*PPTP_VENDOR_DATA_IN, PPTP_VENDOR_DATA_IN, PPTP_VENDOR_DATA_IN structure pointer [Imaging Devices], PTP_VENDOR_DATA_IN, PTP_VENDOR_DATA_IN structure [Imaging Devices], _PTP_VENDOR_DATA_IN, image.ptp_vendor_data_in, ptpusd/PPTP_VENDOR_DATA_IN, ptpusd/PTP_VENDOR_DATA_IN, wiastrct_b0ebb671-78d9-4224-8bde-893fb0afc9f8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ptpusd.h
req.include-header: Ptpusd.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later.
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
-	ptpusd.h
api_name:
-	PTP_VENDOR_DATA_IN
product:
- Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_IN, *PPTP_VENDOR_DATA_IN
---

# _PTP_VENDOR_DATA_IN structure


## -description


The PTP_VENDOR_DATA_IN structure contains information about an arbitrary command that an application issues to the device.


## -struct-fields




### -field OpCode

Specifies the command opcode. These codes are defined in the PIMA 15740:2000 standard.


### -field SessionId

Specifies the session ID. This member is not currently used by the PTP driver and should be set to 0.


### -field TransactionId

Specifies the transaction ID. This member is not currently used by the PTP driver and should be set to 0.


### -field Params

Is an array consisting of PTP_MAX_PARAMS (defined in <i>Ptpusd.h</i>) elements, representing the parameters of the command.


### -field NumParams

Specifies the actual number of elements in the <b>Params</b> array.


### -field NextPhase

Indicates whether to read data from the device, write data to the device, or neither. This member can be set to one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PTP_NEXTPHASE_NO_DATA

</td>
<td>
No data is to be read from or written to the device.

</td>
</tr>
<tr>
<td>
PTP_NEXTPHASE_READ_DATA

</td>
<td>
Read data from the device.

</td>
</tr>
<tr>
<td>
PTP_NEXTPHASE_WRITE_DATA

</td>
<td>
Write data to the device.

</td>
</tr>
</table>
 


### -field VendorWriteData

Is an array containing an (optional) first byte to write to the device.


## -remarks



See <a href="https://msdn.microsoft.com/3d360a9f-5a65-452b-a8ad-080dc7d8c8f5">Vendor-Extended Commands</a> for more information and example code that uses this structure. 

For more information about the opcodes used in the <b>OpCode</b> member, see PIMA 15740:2000, <i>Photography </i>−<i> Electronic still picture imaging </i>−<i> Picture Transfer Protocol (PTP) for Digital Still Photography Devices</i>,<i> First Edition</i>, July 5, 2000, http://www.pima.net/standards/it10/PIMA15740/. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546452">PTP_VENDOR_DATA_OUT</a>
 

 

