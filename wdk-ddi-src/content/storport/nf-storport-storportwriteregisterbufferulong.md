---
UID: NF:storport.StorPortWriteRegisterBufferUlong
title: StorPortWriteRegisterBufferUlong macro (storport.h)
description: The StorPortWriteRegisterBufferUlong routine transfers a given number of ULONG values from a buffer to the HBA.
old-location: storage\storportwriteregisterbufferulong.htm
tech.root: storage
ms.assetid: a610f6c5-6627-406e-9b33-f321c6d55a89
ms.date: 03/29/2018
ms.keywords: StorPortWriteRegisterBufferUlong, StorPortWriteRegisterBufferUlong routine [Storage Devices], storage.storportwriteregisterbufferulong, storport/StorPortWriteRegisterBufferUlong, storprt_f43e38af-b5f2-4727-990c-dc0cb79bbc09.xml
ms.topic: macro
f1_keywords:
 - "storport/StorPortWriteRegisterBufferUlong"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortWriteRegisterBufferUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWriteRegisterBufferUlong macro


## -description


The <b>StorPortWriteRegisterBufferUlong</b> routine transfers a given number of ULONG values from a buffer to the HBA.


## -parameters




### -param h

<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportinitialize"><b>StorPortInitialize</b></a>. The port driver frees this memory when it removes the device. </p>


### -param r

<p>Pointer to the register. The given <i>Register</i> must be in a mapped memory space range that was returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportgetdevicebase"><b>StorPortGetDeviceBase</b></a>. </p>


### -param b

<p>Pointer to a buffer containing the data to be written.</p>


### -param c

<p>Specifies the number of ULONG values to be transferred to the HBA.</p>






## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportwriteregisterbufferulong">StorPortWriteRegisterBufferUlong</a>
 

 

