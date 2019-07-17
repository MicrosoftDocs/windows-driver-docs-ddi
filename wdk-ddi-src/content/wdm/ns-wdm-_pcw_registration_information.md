---
UID: NS:wdm._PCW_REGISTRATION_INFORMATION
title: _PCW_REGISTRATION_INFORMATION (wdm.h)
description: The PCW_REGISTRATION_INFORMATION structure supplies details about the provider and the counter set.
old-location: devtest\pcw_registration_information.htm
tech.root: devtest
ms.assetid: f5305351-10b4-47e6-a8b6-e1a91c605ca9
ms.date: 02/23/2018
ms.keywords: "*PPCW_REGISTRATION_INFORMATION, PCW_REGISTRATION_INFORMATION, PCW_REGISTRATION_INFORMATION structure [Driver Development Tools], PPCW_REGISTRATION_INFORMATION, PPCW_REGISTRATION_INFORMATION structure pointer [Driver Development Tools], _PCW_REGISTRATION_INFORMATION, devtest.pcw_registration_information, km_pcw_a740182f-4844-4a98-9493-522087a3d27c.xml, wdm/PCW_REGISTRATION_INFORMATION, wdm/PPCW_REGISTRATION_INFORMATION"
ms.topic: struct
f1_keywords:
 - "wdm/PCW_REGISTRATION_INFORMATION"
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
- PCW_REGISTRATION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PCW_REGISTRATION_INFORMATION, *PPCW_REGISTRATION_INFORMATION
---

# _PCW_REGISTRATION_INFORMATION structure


## -description


The PCW_REGISTRATION_INFORMATION structure supplies details about the provider and the counter set. 


## -struct-fields




### -field Version

The numeric value that specifies the version of Performance Counters for Windows (PCW) that the provider supports.


### -field Name

A pointer to the string that contains the name of the counter set to register.


### -field CounterCount

The number of counters that are exposed by this registration.


### -field Counters

A pointer to the array that describes the counters.


### -field Callback

A pointer to the optional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pcw_callback">PcwCallback</a> function that notifies the provider about events related to this counter set.


### -field CallbackContext

A pointer to the callback context.  


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pcwregister">PcwRegister</a> function takes, as a parameter, a pointer to this structure to serve as the registration handle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_pcw_counter_descriptor">PCW_COUNTER_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-pcw_callback">PcwCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-pcwregister">PcwRegister</a>
 

 

