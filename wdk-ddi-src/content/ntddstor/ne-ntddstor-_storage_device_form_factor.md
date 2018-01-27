---
UID: NE:ntddstor._STORAGE_DEVICE_FORM_FACTOR
title: _STORAGE_DEVICE_FORM_FACTOR
author: windows-driver-content
description: Indicates the form factor of a storage device.
old-location: storage\storage_device_form_factor.htm
old-project: storage
ms.assetid: EE59767B-2504-4E5F-A442-60EEBEE70B59
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: FormFactor1_8Less, FormFactorM_2, ntddstor/FormFactorUnknown, ntddstor/FormFactorM_2, PSTORAGE_DEVICE_FORM_FACTOR, *PSTORAGE_DEVICE_FORM_FACTOR, FormFactor1_8, FormFactormSata, ntddstor/FormFactor3_5, _STORAGE_DEVICE_FORM_FACTOR, ntddstor/FormFactormSata, ntddstor/FormFactor1_8Less, FormFactorMemoryCard, ntddstor/FormFactorPCIeBoard, FormFactorUnknown, ntddstor/PSTORAGE_DEVICE_FORM_FACTOR, FormFactor3_5, ntddstor/FormFactor1_8, ntddstor/FormFactorEmbedded, FormFactorDimm, ntddstor/FormFactorDimm, STORAGE_DEVICE_FORM_FACTOR, FormFactorPCIeBoard, STORAGE_DEVICE_FORM_FACTOR enumeration [Storage Devices], ntddstor/STORAGE_DEVICE_FORM_FACTOR, FormFactorEmbedded, ntddstor/FormFactorMemoryCard, FormFactor2_5, ntddstor/FormFactor2_5, storage.storage_device_form_factor, PSTORAGE_DEVICE_FORM_FACTOR enumeration pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddstor.h
apiname: 
-	STORAGE_DEVICE_FORM_FACTOR
product: Windows
targetos: Windows
req.typenames: *PSTORAGE_DEVICE_FORM_FACTOR, STORAGE_DEVICE_FORM_FACTOR
---

# _STORAGE_DEVICE_FORM_FACTOR enumeration


## -description


Indicates the form factor of a storage device.


## -syntax


````
typedef enum _STORAGE_DEVICE_FORM_FACTOR { 
  FormFactorUnknown     = 0, // 0x0
  FormFactor3_5,
  FormFactor2_5,
  FormFactor1_8,
  FormFactor1_8Less,
  FormFactorEmbedded,
  FormFactorMemoryCard,
  FormFactormSata,
  FormFactorM_2,
  FormFactorPCIeBoard,
  FormFactorDimm
} STORAGE_DEVICE_FORM_FACTOR, *PSTORAGE_DEVICE_FORM_FACTOR;
````


## -enum-fields




### -field FormFactorUnknown

Unknown form factor.


### -field FormFactor3_5

3.5 inch nominal form factor.


### -field FormFactor2_5

2.5 inch nominal form factor.


### -field FormFactor1_8

1.8 inch nominal form factor.


### -field FormFactor1_8Less

Less than 1.8 inch nominal form factor.


### -field FormFactorEmbedded

The storage device is embedded on a board.


### -field FormFactorMemoryCard

A memory card, such as SmartMedia or CompactFlash.


### -field FormFactormSata

Mini-SATA (mSATA) form factor.


### -field FormFactorM_2

M.2 form factor.


### -field FormFactorPCIeBoard

PCI Express (PCIe) card form factor.


### -field FormFactorDimm

Dual in-line memory module (DIMM) slot form factor.

