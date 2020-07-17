---
UID: NS:ntifs._WOF_EXTERNAL_FILE_ID
title: _WOF_EXTERNAL_FILE_ID (ntifs.h)
description: The WOF_EXTERNAL_FILE_ID structure contains a file ID that is used to open a handle to a mini-filter or driver.
old-location: ifsk\wof_external_file_id.htm
tech.root: ifsk
ms.assetid: 5C208DF7-C6CB-419D-B775-74E09DC4D448
ms.date: 04/16/2018
keywords: ["_WOF_EXTERNAL_FILE_ID structure"]
ms.keywords: "*PWOF_EXTERNAL_FILE_ID, PWOF_EXTERNAL_FILE_ID, PWOF_EXTERNAL_FILE_ID structure pointer [Installable File System Drivers], WOF_EXTERNAL_FILE_ID, WOF_EXTERNAL_FILE_ID structure [Installable File System Drivers], _WOF_EXTERNAL_FILE_ID, ifsk.wof_external_file_id, ntifs/PWOF_EXTERNAL_FILE_ID, ntifs/WOF_EXTERNAL_FILE_ID"
f1_keywords:
 - "ntifs/WOF_EXTERNAL_FILE_ID"
 - "WOF_EXTERNAL_FILE_ID"
req.header: ntifs.h
req.include-header: Windows.h, WinIoCtl.h, Ntifs.h, Windows.h, WinIoCtl.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
- ntifs.h
api_name:
- WOF_EXTERNAL_FILE_ID
product:
- Windows
targetos: Windows
req.typenames: WOF_EXTERNAL_FILE_ID, *PWOF_EXTERNAL_FILE_ID
---

# _WOF_EXTERNAL_FILE_ID structure


## -description


The <b>WOF_EXTERNAL_FILE_ID</b> structure contains a file ID that is used to open a handle to a mini-filter or driver.


## -struct-fields




### -field FileId

The file ID used with the <b>FILE_OPEN_BY_FILE_ID</b> flag to open a file with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> functions.


## -remarks



Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcreatefile">FltCreateFile</a> function to open a handle to a minifilter driver and use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> function to open a handle to a driver.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_wof_external_info">WOF_EXTERNAL_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_wof_version_info">WOF_VERSION_INFO</a>
 

 

