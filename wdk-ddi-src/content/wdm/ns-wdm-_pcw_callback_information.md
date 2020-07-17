---
UID: NS:wdm._PCW_CALLBACK_INFORMATION
title: _PCW_CALLBACK_INFORMATION (wdm.h)
description: The PCW_CALLBACK_INFORMATION union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the PcwCallback function.
old-location: devtest\pcw_callback_information.htm
tech.root: devtest
ms.assetid: cc1882a9-eba7-494c-9047-5c97b1e3c19b
ms.date: 02/23/2018
keywords: ["_PCW_CALLBACK_INFORMATION structure"]
ms.keywords: "*PPCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION, PCW_CALLBACK_INFORMATION union [Driver Development Tools], PPCW_CALLBACK_INFORMATION, PPCW_CALLBACK_INFORMATION union pointer [Driver Development Tools], _PCW_CALLBACK_INFORMATION, devtest.pcw_callback_information, km_pcw_d44ee92a-c8a0-4da9-8739-cf5443ee2d85.xml, wdm/PCW_CALLBACK_INFORMATION, wdm/PPCW_CALLBACK_INFORMATION"
f1_keywords:
 - "wdm/PCW_CALLBACK_INFORMATION"
 - "PCW_CALLBACK_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdm.h
api_name:
- PCW_CALLBACK_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PCW_CALLBACK_INFORMATION, *PPCW_CALLBACK_INFORMATION
---

# _PCW_CALLBACK_INFORMATION structure


## -description


The <b>PCW_CALLBACK_INFORMATION</b> union supplies details about the notification to send. A provider passes a pointer to this union as a parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pcw_callback">PcwCallback</a> function. 


## -struct-fields




### -field AddCounter

The PCW_COUNTER_INFORMATION structure that identifies the counter being added. 


### -field RemoveCounter

The PCW_COUNTER_INFORMATION structure that identifies the counter being removed. 


### -field EnumerateInstances

The PCW_MASK_INFORMATION structure that identifies the instances of the counter set.


### -field CollectData

The PCW_MASK_INFORMATION structure that identifies the instance of the counter set and its buffer.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pcw_counter_information">PCW_COUNTER_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_pcw_mask_information">PCW_MASK_INFORMATION</a>
 

 

