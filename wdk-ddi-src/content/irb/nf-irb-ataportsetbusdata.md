---
UID: NF:irb.AtaPortSetBusData
title: AtaPortSetBusData function (irb.h)
description: The AtaPortSetBusData routine stores the data at Buffer in the indicated device's PCI configuration space at an offset that is specified in ConfigDataOffset.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\ataportsetbusdata.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["AtaPortSetBusData function"]
ms.keywords: AtaPortSetBusData, AtaPortSetBusData routine [Storage Devices], atartns_85424997-1f6e-4f48-98f0-e92a7312e62a.xml, irb/AtaPortSetBusData, storage.ataportsetbusdata
req.header: irb.h
req.include-header: Ata.h, Irb.h
req.target-type: Desktop
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
req.lib: Pciidex.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - AtaPortSetBusData
 - irb/AtaPortSetBusData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Pciidex.lib
 - Pciidex.dll
api_name:
 - AtaPortSetBusData
---

# AtaPortSetBusData function

## -description

The **AtaPortSetBusData** routine stores the data at **Buffer** in the indicated device's PCI configuration space at an offset that is specified in **ConfigDataOffset**.

> [!NOTE]
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](/windows-hardware/drivers/storage/storport-driver) and [Storport miniport](/windows-hardware/drivers/storage/storport-miniport-drivers) driver models.

## -parameters

### -param ControllerExtension

[in] A pointer to the controller extension.

### -param Buffer

[in] A pointer to the buffer that contains the data to write to the device's PCI bus configuration space.

### -param ConfigDataOffset

[in] Specifies an offset into the device's PCI bus configuration data space where the data is updated.

### -param BufferLength

[in] Specifies the length, in bytes, of the buffer that **Buffer** points to.

## -returns

**AtaPortSetBusData** returns the amount of the data that was written in bytes.

## -remarks

**AtaPortSetBusData** completes a bitwise OR, one byte at a time, of the current PCI configuration space data with the new data in **Buffer**. Only those bits not indicated by **DataMask** are left untouched. The byte of data that follows **ConfigDataOffset**, therefore, is updated as follows:

``` C
ConfigDataOffest[i] = 
    (ConfigDataOffest[i] & ~DataMask[i]) | 
    (DataMask[i] & Buffer[i])
```

## -see-also

[**AtaPortGetBusData**](/windows-hardware/drivers/ddi/irb/nf-irb-ataportgetbusdata)
