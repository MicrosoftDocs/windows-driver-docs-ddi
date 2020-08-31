---
UID: NS:irb._IDE_TASK_FILE
title: _IDE_TASK_FILE (irb.h)
description: The IDE_TASK_FILE structure contains the current and previous IDE task file.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_task_file.htm
tech.root: storage
ms.assetid: f18b46c0-975b-49ba-b398-45f2a44d6d3b
ms.date: 03/29/2018
keywords: ["IDE_TASK_FILE structure"]
ms.keywords: "*PIDE_TASK_FILE, IDE_TASK_FILE, IDE_TASK_FILE structure [Storage Devices], PIDE_TASK_FILE, PIDE_TASK_FILE structure pointer [Storage Devices], _IDE_TASK_FILE, irb/IDE_TASK_FILE, irb/PIDE_TASK_FILE, storage.ide_task_file, structs-ATA_0d96e047-8840-46cd-9df1-606ca70edb9e.xml"
req.header: irb.h
req.include-header: Irb.h
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
targetos: Windows
req.typenames: IDE_TASK_FILE, *PIDE_TASK_FILE
f1_keywords:
 - _IDE_TASK_FILE
 - irb/_IDE_TASK_FILE
 - PIDE_TASK_FILE
 - irb/PIDE_TASK_FILE
 - IDE_TASK_FILE
 - irb/IDE_TASK_FILE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - irb.h
api_name:
 - IDE_TASK_FILE
---

# _IDE_TASK_FILE structure


## -description

The IDE_TASK_FILE structure contains the current and previous IDE task file.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields

### -field Current

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ideregisters">IDEREGISTERS</a> that holds the current contents of the ATA task file registers.

### -field Previous

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ideregisters">IDEREGISTERS</a> that holds the previous contents of the ATA task file registers in the case of a 48-bit LBA command.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/irb/ns-irb-_ideregisters">IDEREGISTERS</a>

