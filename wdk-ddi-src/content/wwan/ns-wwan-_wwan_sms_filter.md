---
UID: NS:wwan._WWAN_SMS_FILTER
title: "_WWAN_SMS_FILTER"
author: windows-driver-content
description: The WWAN_SMS_FILTER structure represents the filter to apply to SMS messages on the MB device.
old-location: netvista\wwan_sms_filter.htm
old-project: netvista
ms.assetid: 798101da-51be-416d-ac56-2f55a21e8ea8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_SMS_FILTER, PWWAN_SMS_FILTER, PWWAN_SMS_FILTER structure pointer [Network Drivers Starting with Windows Vista], WWAN_SMS_FILTER, WWAN_SMS_FILTER structure [Network Drivers Starting with Windows Vista], WwanRef_1bec8893-7ce8-4d8c-aea1-d1c76b0013fc.xml, _WWAN_SMS_FILTER, netvista.wwan_sms_filter, wwan/PWWAN_SMS_FILTER, wwan/WWAN_SMS_FILTER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	wwan.h
api_name:
-	WWAN_SMS_FILTER
product:
- Windows
targetos: Windows
req.typenames: WWAN_SMS_FILTER, *PWWAN_SMS_FILTER
req.product: Windows 10 or later.
---

# _WWAN_SMS_FILTER structure


## -description


The WWAN_SMS_FILTER structure represents the filter to apply to SMS messages on the MB device.


## -struct-fields




### -field Flag

A value from the WWAN_SMS_FLAG enumeration that represents what filter to use to display SMS
     messages for.


### -field MessageIndex

A value between 1 and 
     <i>ulMaxMessageIndex</i> that is an index into the device's message store.
     

This value in this member is valid only if 
     <b>Flag</b> is set to 
     <b>WwanSmsFlagIndex</b>. The MB Service sets this member if 
     <b>Flag</b> is set to 
     <b>WwanSmsFlagIndex</b>. For all flags other than 
     <b>WwanSmsFlagIndex</b>, the MB Service sets this index to WWAN_MESSAGE_INDEX_NONE.


## -remarks



When 
    <b>Flag</b> is 
    <b>WwanSmsFlagIndex</b>, the filter identifies the SMS message specified by 
    <b>MessageIndex</b> .




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567938">NDIS_WWAN_SMS_DELETE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571246">WWAN_SMS_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571249">WWAN_SMS_READ</a>
 

 

