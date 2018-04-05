---
UID: NS:61883._AV_PCR
title: "_AV_PCR"
author: windows-driver-content
description: The AV_PCR structure specifies settings for an input or output plug.
old-location: ieee\av_pcr.htm
old-project: IEEE
ms.assetid: f6d3f95b-7484-4a6b-9b7e-69f6172b7a12
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PAV_PCR, 61883/AV_PCR, 61883/PAV_PCR, 61883_structures_d8602c71-aca5-427d-a8bf-d1da914ebacc.xml, AV_PCR, AV_PCR structure [Buses], IEEE.av_pcr, PAV_PCR, PAV_PCR structure pointer [Buses], _AV_PCR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
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
-	61883.h
api_name:
-	AV_PCR
product:
- Windows
targetos: Windows
req.typenames: AV_PCR, *PAV_PCR
---

# _AV_PCR structure


## -description


The AV_PCR structure specifies settings for an input or output plug.


## -struct-fields






#### - iPCR

Contains an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537348">IPCR</a> structure that contains initialization values for an input plug.


#### - oPCR

Contains an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537441">OPCR</a> structure that contains initialization values for an output plug. 


#### - ulongData

Reserved for internal use.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536961">Av61883_CreatePlug</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536995">Av61883_SetPlug</a>
 

 

