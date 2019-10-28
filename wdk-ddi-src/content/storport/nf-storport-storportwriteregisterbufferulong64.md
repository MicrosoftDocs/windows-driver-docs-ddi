---
UID: NF:storport.StorPortWriteRegisterBufferUlong64
title: StorPortWriteRegisterBufferUlong64 macro (storport.h)
description: This StorPortWriteRegisterBufferUlong64 routine writes a number of ULONG64 values from a the specified 64-bit register address.
old-location: storage\storportwriteregisterbufferulong64.htm
tech.root: storage
ms.assetid: 3C36DB8F-46C2-4E81-B2F3-6DE78D91566E
ms.date: 03/29/2018
ms.keywords: StorPortWriteRegisterBufferUlong64, StorPortWriteRegisterBufferUlong64 routine [Storage Devices], storage.storportwriteregisterbufferulong64, storport/StorPortWriteRegisterBufferUlong64
ms.topic: macro
f1_keywords:
 - "storport/StorPortWriteRegisterBufferUlong64"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
- storport.h
api_name:
- StorPortWriteRegisterBufferUlong64
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWriteRegisterBufferUlong64 macro


## -description


This <b>StorPortWriteRegisterBufferUlong64</b> routine writes a number of <b>ULONG64</b> values from a the specified 64-bit register address.
 


## -parameters




### -param h


<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize"><b>StorPortInitialize</b></a>. The port driver frees this memory when it removes the device. </p>

### -param r

<p>Pointer to the register where the data is written to. The given <i>Register</i> must be in a mapped memory-space range returned by [**StorPortGetDeviceBase**](nf-storport-storportgetdevicebase.md).

### -param b

<p>Pointer to the buffer to write the <b>ULONG64</b> values from.</p>

### -param c

<p>Specifies the number of data values to write. Each data item has a size of <b>sizeof</b>(ULONG64). </p>






## -remarks



The <b>StorPortWriteRegisterBufferUlong64</b> routine is only available on the 64-bit version of Windows.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportreadregisterbufferulong64">StorPortReadRegisterBufferUlong64</a>
 

 

