---
UID: NS:wdm._CM_EISA_FUNCTION_INFORMATION
title: "_CM_EISA_FUNCTION_INFORMATION"
author: windows-driver-content
description: The CM_EISA_FUNCTION_INFORMATION structure defines detailed EISA configuration information returned by HalGetBusData for the input BusDataType EisaConfiguration, or by HalGetBusDataByOffset for the input BusDataType EisaConfiguration and the Offset zero, assuming the caller-allocated Buffer is of sufficient Length.
old-location: kernel\cm_eisa_function_information.htm
old-project: kernel
ms.assetid: 06034776-4faf-4918-b9ec-bc095455cf14
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PCM_EISA_FUNCTION_INFORMATION, CM_EISA_FUNCTION_INFORMATION, CM_EISA_FUNCTION_INFORMATION structure [Kernel-Mode Driver Architecture], PCM_EISA_FUNCTION_INFORMATION, PCM_EISA_FUNCTION_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _CM_EISA_FUNCTION_INFORMATION, kernel.cm_eisa_function_information, kstruct_a_0ecf5914-f26d-415f-b410-ff2f131b2b08.xml, wdm/CM_EISA_FUNCTION_INFORMATION, wdm/PCM_EISA_FUNCTION_INFORMATION"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CM_EISA_FUNCTION_INFORMATION
product: Windows
targetos: Windows
req.typenames: CM_EISA_FUNCTION_INFORMATION, *PCM_EISA_FUNCTION_INFORMATION
---

# _CM_EISA_FUNCTION_INFORMATION structure


## -description


The <b>CM_EISA_FUNCTION_INFORMATION</b> structure defines detailed EISA configuration information returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a> for the input <i>BusDataType </i><b>EisaConfiguration</b>, or by <b>HalGetBusDataByOffset</b> for the input <i>BusDataType </i><b>EisaConfiguration</b> and the <i>Offset</i> zero, assuming the caller-allocated <i>Buffer</i> is of sufficient <i>Length</i>.


## -struct-fields




### -field CompressedId

The EISA compressed identification of the device at this slot. The value is identical to the <b>CompressedId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541941">CM_EISA_SLOT_INFORMATION</a> structure.


### -field IdSlotFlags1

The EISA slot identification flags.


### -field IdSlotFlags2

The EISA slot identification flags.


### -field MinorRevision

Information supplied by the manufacturer. 


### -field MajorRevision

Information supplied by the manufacturer. 


### -field Selections

The EISA selections for the device.


### -field FunctionFlags

Indicates which of the members has available information. Callers can use the following system-defined masks to determine whether a particular type of configuration information can be or has been returned by <b>HalGetBusData</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>:

EISA_FUNCTION_ENABLED

EISA_FREE_FORM_DATA

EISA_HAS_PORT_INIT_ENTRY

EISA_HAS_PORT_RANGE

EISA_HAS_DMA_ENTRY

EISA_HAS_IRQ_ENTRY

EISA_HAS_MEMORY_ENTRY

EISA_HAS_TYPE_ENTRY

EISA_HAS_INFORMATION

The EISA_HAS_INFORMATION mask is a combination of the following:

EISA_HAS_PORT_RANGE

EISA_HAS_DMA_ENTRY

EISA_HAS_IRQ_ENTRY

EISA_HAS_MEMORY_ENTRY

EISA_HAS_TYPE_ENTRY


### -field TypeString

Specifies the type of device.


### -field EisaMemory

Describes the EISA device memory configuration information, defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _EISA_MEMORY_CONFIGURATION {
    EISA_MEMORY_TYPE ConfigurationByte;
    UCHAR DataSize;
    USHORT AddressLowWord;
    UCHAR AddressHighByte;
    USHORT MemorySize;
} EISA_MEMORY_CONFIGURATION, *PEISA_MEMORY_CONFIGURATION;</pre>
</td>
</tr>
</table></span></div>

### -field EisaIrq

Describes the EISA interrupt configuration information, defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _EISA_IRQ_CONFIGURATION {
    EISA_IRQ_DESCRIPTOR ConfigurationByte;
    UCHAR Reserved;
} EISA_IRQ_CONFIGURATION, *PEISA_IRQ_CONFIGURATION;</pre>
</td>
</tr>
</table></span></div>

### -field EisaDma

Describes the EISA DMA configuration information, defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _EISA_DMA_CONFIGURATION {
    DMA_CONFIGURATION_BYTE0 ConfigurationByte0;
    DMA_CONFIGURATION_BYTE1 ConfigurationByte1;
} EISA_DMA_CONFIGURATION, *PEISA_DMA_CONFIGURATION;</pre>
</td>
</tr>
</table></span></div>

### -field EisaPort

Describes the EISA device port configuration information, defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _EISA_PORT_CONFIGURATION {
    EISA_PORT_DESCRIPTOR Configuration;
    USHORT PortAddress;
} EISA_PORT_CONFIGURATION, *PEISA_PORT_CONFIGURATION;</pre>
</td>
</tr>
</table></span></div>

### -field InitializationData

Vendor-supplied, device-specific initialization data, if any. 


## -remarks



The information returned by <b>HalGetBusData</b> or <b>HalGetBusDataByOffset</b> in <b>CM_EISA_FUNCTION_INFORMATION</b> and/or in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541941">CM_EISA_SLOT_INFORMATION</a> header immediately preceding it is read-only.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541941">CM_EISA_SLOT_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546599">HalGetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546606">HalGetBusDataByOffset</a>
 

 

