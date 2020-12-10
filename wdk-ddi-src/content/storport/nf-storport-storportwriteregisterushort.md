---
UID: NF:storport.StorPortWriteRegisterUshort
title: StorPortWriteRegisterUshort macro (storport.h)
description: The StorPortWriteRegisterUshort routine transfers a ULONG value to the indicated HBA register address.
old-location: storage\storportwriteregisterushort.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortWriteRegisterUshort macro"]
ms.keywords: StorPortWriteRegisterUshort, StorPortWriteRegisterUshort routine [Storage Devices], storage.storportwriteregisterushort, storport/StorPortWriteRegisterUshort, storprt_f4cd6932-3fd0-435f-87f3-7241a5778073.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortWriteRegisterUshort
 - storport/StorPortWriteRegisterUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Storport.lib
 - Storport.dll
api_name:
 - StorPortWriteRegisterUshort
---

# StorPortWriteRegisterUshort macro


## -description

The <b>StorPortWriteRegisterUshort</b> routine transfers a ULONG value to the indicated HBA register address.

## -parameters

### -param h

<p>A pointer to the hardware device extension. This is a per HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize"><b>StorPortInitialize</b></a>. The port driver frees this memory when it removes the device. </p>

### -param r

<p>Pointer to the register. The given <i>Register</i> must be in a mapped memory space range returned by <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportgetdevicebase"><b>StorPortGetDeviceBase</b></a>. </p>

### -param v

<p>Specifies the USHORT value to be written to the HBA's register.</p>

## -see-also

<a href="/windows-hardware/drivers/ddi/srb/nf-srb-scsiportwriteregisterushort">ScsiPortWriteRegisterUshort</a>
