---
UID: NS:wdm._PCW_DATA
title: "_PCW_DATA"
author: windows-driver-content
description: The PCW_DATA structure describes the array of data blocks that are associated with an instance.
old-location: devtest\pcw_data.htm
tech.root: devtest
ms.assetid: c2da567a-cea6-497a-b50f-848ecac20b30
ms.date: 02/23/2018
ms.keywords: "*PPCW_DATA, PCW_DATA, PCW_DATA structure [Driver Development Tools], PPCW_DATA, PPCW_DATA structure pointer [Driver Development Tools], _PCW_DATA, devtest.pcw_data, km_pcw_69759b50-4312-4997-ba43-4ce30941d502.xml, wdm/PCW_DATA, wdm/PPCW_DATA"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 or later versions of Windows.
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
-	PCW_DATA
product:
- Windows
targetos: Windows
req.typenames: PCW_DATA, *PPCW_DATA
---

# _PCW_DATA structure


## -description


The PCW_DATA structure describes the array of data blocks that are associated with an instance.


## -struct-fields




### -field Data

A <b>const</b> pointer to a buffer of <b>Size</b> bytes.


### -field Size

A numeric value that specifies the size, in bytes, associated with the instance of the counter set.

