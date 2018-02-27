---
UID: NS:irb._IDE_TASK_FILE
title: "_IDE_TASK_FILE"
author: windows-driver-content
description: The IDE_TASK_FILE structure contains the current and previous IDE task file.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_task_file.htm
old-project: storage
ms.assetid: f18b46c0-975b-49ba-b398-45f2a44d6d3b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PIDE_TASK_FILE, IDE_TASK_FILE, IDE_TASK_FILE structure [Storage Devices], PIDE_TASK_FILE, PIDE_TASK_FILE structure pointer [Storage Devices], _IDE_TASK_FILE, irb/IDE_TASK_FILE, irb/PIDE_TASK_FILE, storage.ide_task_file, structs-ATA_0d96e047-8840-46cd-9df1-606ca70edb9e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	IDE_TASK_FILE
product: Windows
targetos: Windows
req.typenames: IDE_TASK_FILE, *PIDE_TASK_FILE
---

# _IDE_TASK_FILE structure


## -description


The IDE_TASK_FILE structure contains the current and previous IDE task file.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IDE_TASK_FILE {
  IDEREGISTERS Current;
  IDEREGISTERS Previous;
} IDE_TASK_FILE, *PIDE_TASK_FILE;
````


## -struct-fields




### -field Current

Contains a structure of type <a href="..\irb\ns-irb-_ideregisters.md">IDEREGISTERS</a> that holds the current contents of the ATA task file registers.


### -field Previous

Contains a structure of type <a href="..\irb\ns-irb-_ideregisters.md">IDEREGISTERS</a> that holds the previous contents of the ATA task file registers in the case of a 48-bit LBA command.


## -see-also

<a href="..\irb\ns-irb-_ideregisters.md">IDEREGISTERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_TASK_FILE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

