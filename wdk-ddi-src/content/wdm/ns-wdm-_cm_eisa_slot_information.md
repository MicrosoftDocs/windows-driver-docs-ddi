---
UID: NS:wdm._CM_EISA_SLOT_INFORMATION
title: "_CM_EISA_SLOT_INFORMATION"
author: windows-driver-content
description: The CM_EISA_SLOT_INFORMATION structure defines EISA configuration header information returned by HalGetBusData for the input BusDataType = EisaConfiguration, or by HalGetBusDataByOffset for the inputs BusDataType = EisaConfiguration and Offset = 0, assuming the caller-allocated Buffer is of sufficient Length.
old-location: kernel\cm_eisa_slot_information.htm
old-project: kernel
ms.assetid: 443b6ed8-1d44-466f-93b0-bb8cd42aefaa
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCM_EISA_SLOT_INFORMATION, CM_EISA_SLOT_INFORMATION, CM_EISA_SLOT_INFORMATION structure [Kernel-Mode Driver Architecture], PCM_EISA_SLOT_INFORMATION, PCM_EISA_SLOT_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _CM_EISA_SLOT_INFORMATION, kernel.cm_eisa_slot_information, kstruct_a_07946ecf-4bcd-4626-a070-e3bca212c0ef.xml, wdm/CM_EISA_SLOT_INFORMATION, wdm/PCM_EISA_SLOT_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CM_EISA_SLOT_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: CM_EISA_SLOT_INFORMATION, *PCM_EISA_SLOT_INFORMATION
req.product: Windows 10 or later.
---

# _CM_EISA_SLOT_INFORMATION structure


## -description


The <b>CM_EISA_SLOT_INFORMATION</b> structure defines EISA configuration header information returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> for the input <i>BusDataType</i> =  <b>EisaConfiguration</b>, or by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a> for the inputs <i>BusDataType</i> =  <b>EisaConfiguration</b> and <i>Offset</i> = 0, assuming the caller-allocated <i>Buffer</i> is of sufficient <i>Length</i>.


## -struct-fields




### -field ReturnCode

Contains a status code if an error occurs when the EISA BIOS is queried. Possible status codes include the following:

<ul>
<li>EISA_INVALID_SLOT</li>
<li>EISA_INVALID_FUNCTION</li>
<li>EISA_INVALID_CONFIGURATION</li>
<li>EISA_EMPTY_SLOT</li>
<li>EISA_INVALID_BIOS_CALL</li>
</ul>

### -field ReturnFlags

The return flags.


### -field MajorRevision

Information supplied by the manufacturer.


### -field MinorRevision

Information supplied by the manufacturer.


### -field Checksum

The checksum value, allowing validation of the configuration data.


### -field NumberFunctions

The number at this slot.


### -field FunctionInformation

Whether there is available <a href="https://msdn.microsoft.com/library/windows/hardware/ff541930">CM_EISA_FUNCTION_INFORMATION</a> for this slot.


### -field CompressedId

The EISA compressed identification of the device at this slot. This value is identical to the <b>CompressedId</b> member of the <b>CM_EISA_FUNCTION_INFORMATION</b> structure. This member can be read to determine whether the caller should call <b>HalGetBusData</b> or <b>HalGetBusDataByOffset</b> again with sufficient buffer space to get more detailed <b>CM_EISA_FUNCTION_INFORMATION</b> for a device it supports.


## -remarks



The information returned by <b>HalGetBusData</b> or <b>HalGetBusDataByOffset</b> in <b>CM_EISA_SLOT_INFORMATION</b> and in <b>CM_EISA_FUNCTION_INFORMATION</b> immediately following it is read-only.

The driver of an EISA device might call <b>HalGetBusData</b> or <b>HalGetBusDataByOffset</b> for each slot on each EISA bus in the system, requesting only <b>CM_EISA_SLOT_INFORMATION</b> in order to find the device(s) it supports by examining the returned <b>CompressedId</b> values. Then, such a driver could allocate sufficient buffer space to call <b>HalGetBusData(ByOffset)</b> again for <b>CM_EISA_SLOT_INFORMATION</b> and <b>CM_EISA_FUNCTION_INFORMATION</b> at slots where its device(s) can be found.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541930">CM_EISA_FUNCTION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>
 

 

