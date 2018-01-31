---
UID: NS:ptpusd._PTP_VENDOR_DATA_OUT
title: "_PTP_VENDOR_DATA_OUT"
author: windows-driver-content
description: The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.
old-location: image\ptp_vendor_data_out.htm
old-project: image
ms.assetid: 2585c7ce-6dba-491a-86c1-5ee69f28136f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PPTP_VENDOR_DATA_OUT, _PTP_VENDOR_DATA_OUT, wiastrct_032c0aa0-aec8-440d-b528-de1b739d2e1d.xml, PPTP_VENDOR_DATA_OUT structure pointer [Imaging Devices], PPTP_VENDOR_DATA_OUT, image.ptp_vendor_data_out, ptpusd/PTP_VENDOR_DATA_OUT, PTP_VENDOR_DATA_OUT, PTP_VENDOR_DATA_OUT structure [Imaging Devices], ptpusd/PPTP_VENDOR_DATA_OUT"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ptpusd.h
apiname:
-	PTP_VENDOR_DATA_OUT
product: Windows
targetos: Windows
req.typenames: "*PPTP_VENDOR_DATA_OUT, PTP_VENDOR_DATA_OUT"
req.product: Windows 10 or later.
---

# _PTP_VENDOR_DATA_OUT structure


## -description


The PTP_VENDOR_DATA_OUT structure contains information that the device sends to an application, in response to a command the application issued to the device.


## -syntax


````
typedef struct _PTP_VENDOR_DATA_OUT {
  WORD  ResponseCode;
  DWORD SessionId;
  DWORD TransactionId;
  DWORD Params[PTP_MAX_PARAMS];
  BYTE  VendorReadData[1];
} PTP_VENDOR_DATA_OUT, *PPTP_VENDOR_DATA_OUT;
````


## -struct-fields




#### - ResponseCode

Specifies the response code. These codes are defined in the PIMA 15740:2000 standard.


#### - SessionId

Specifies the session ID. This member is not currently used by the PTP driver and should be set to 0.


#### - TransactionId

Specifies the transaction ID. This member is not currently used by the PTP driver and should be set to 0.


#### - Params

Is an array consisting of PTP_MAX_PARAMS (defined in <i>Ptpusd.h</i>) elements, representing the parameters of the response.


#### - VendorReadData

Is an array containing an (optional) first byte to read from the device.


## -remarks


See <a href="https://msdn.microsoft.com/3d360a9f-5a65-452b-a8ad-080dc7d8c8f5">Vendor-Extended Commands</a> for more information and example code that uses this structure.

For more information about the response codes used in the <b>ResponseCode</b> member, see PIMA 15740:2000, <i>Photography </i>−<i> Electronic still picture imaging </i>−<i> Picture Transfer Protocol (PTP) for Digital Still Photography Devices</i>,<i> First Edition</i>, July 5, 2000, http://www.pima.net/standards/it10/PIMA15740/. 



## -see-also

<a href="..\ptpusd\ns-ptpusd-_ptp_vendor_data_in.md">PTP_VENDOR_DATA_IN</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20PTP_VENDOR_DATA_OUT structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

