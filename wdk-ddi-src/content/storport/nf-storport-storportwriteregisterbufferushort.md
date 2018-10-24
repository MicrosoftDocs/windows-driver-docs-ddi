---
UID: NF:storport.StorPortWriteRegisterBufferUshort
title: StorPortWriteRegisterBufferUshort macro
author: windows-driver-content
description: The StorPortWriteRegisterBufferUshort routine transfers a given number of USHORT values from a buffer to the HBA.
old-location: storage\storportwriteregisterbufferushort.htm
tech.root: storage
ms.assetid: 13da18b3-682f-485a-9d74-0bbff4254862
ms.date: 03/29/2018
ms.keywords: StorPortWriteRegisterBufferUshort, StorPortWriteRegisterBufferUshort routine [Storage Devices], storage.storportwriteregisterbufferushort, storport/StorPortWriteRegisterBufferUshort, storprt_8b227304-10e5-46fc-93e1-41b1c91068b1.xml
ms.topic: macro
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortWriteRegisterBufferUshort
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortWriteRegisterBufferUshort macro


## -description


The <b>StorPortWriteRegisterBufferUshort</b> routine transfers a given number of USHORT values from a buffer to the HBA.


## -parameters




### -param h

<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/Ff567108(v=VS.85).aspx"><b>StorPortInitialize</b></a>. The port driver frees this memory when it removes the device. </p>


### -param r

<p>Pointer to the register. The given <i>Register</i> must be in a mapped memory space range that was returned by <a href="https://msdn.microsoft.com/library/Ff567080(v=VS.85).aspx"><b>StorPortGetDeviceBase</b></a>. </p>


### -param b

<p>Pointer to a buffer containing the data to be written.</p>


### -param c

<p>Specifies the number of USHORT values to be transferred to the HBA.</p>






## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564855">ScsiPortWriteRegisterBufferUshort</a>
 

 

