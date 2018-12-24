---
UID: NS:ptpusd._PTP_VENDOR_DATA_OUT
title: "_PTP_VENDOR_DATA_OUT"
description: The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.
old-location: image\ptp_vendor_data_out.htm
tech.root: image
ms.assetid: 2585c7ce-6dba-491a-86c1-5ee69f28136f
ms.date: 05/03/2018
ms.keywords: "*PPTP_VENDOR_DATA_OUT, PPTP_VENDOR_DATA_OUT, PPTP_VENDOR_DATA_OUT structure pointer [Imaging Devices], PTP_VENDOR_DATA_OUT, PTP_VENDOR_DATA_OUT structure [Imaging Devices], _PTP_VENDOR_DATA_OUT, image.ptp_vendor_data_out, ptpusd/PPTP_VENDOR_DATA_OUT, ptpusd/PTP_VENDOR_DATA_OUT, wiastrct_032c0aa0-aec8-440d-b528-de1b739d2e1d.xml"
ms.topic: struct
req.header: ptpusd.h
req.include-header: Ptpusd.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
-	PTP_VENDOR_DATA_OUT
product:
- Windows
targetos: Windows
req.typenames: PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT
---

# _PTP_VENDOR_DATA_OUT structure


## -description


The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.


## -struct-fields




### -field ResponseCode

Specifies the response code. These codes are defined in the PIMA 15740:2000 standard.


### -field SessionId

Specifies the session ID. This member is not currently used by the PTP driver and should be set to 0.


### -field TransactionId

Specifies the transaction ID. This member is not currently used by the PTP driver and should be set to 0.


### -field Params

Is an array consisting of PTP_MAX_PARAMS (defined in <i>Ptpusd.h</i>) elements, representing the parameters of the response.


### -field VendorReadData

Is an array containing an (optional) first byte to read from the device.


## -remarks



See <a href="https://msdn.microsoft.com/3d360a9f-5a65-452b-a8ad-080dc7d8c8f5">Vendor-Extended Commands</a> for more information and example code that uses this structure.

For more information about the response codes used in the <b>ResponseCode</b> member, see PIMA 15740:2000, <i>Photography </i>−<i> Electronic still picture imaging </i>−<i> Picture Transfer Protocol (PTP) for Digital Still Photography Devices</i>,<i> First Edition</i>, July 5, 2000, http://www.pima.net/standards/it10/PIMA15740/. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546450">PTP_VENDOR_DATA_IN</a>
 

 

