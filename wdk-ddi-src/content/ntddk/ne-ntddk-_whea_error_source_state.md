---
UID: NE:ntddk._WHEA_ERROR_SOURCE_STATE
title: "_WHEA_ERROR_SOURCE_STATE"
author: windows-driver-content
description: The WHEA_ERROR_SOURCE_STATE enumeration defines the different runtime states for an error source.
old-location: whea\whea_error_source_state.htm
old-project: whea
ms.assetid: 7be90712-9f6f-4998-a8ca-148ff900c82c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWHEA_ERROR_SOURCE_STATE, PWHEA_ERROR_SOURCE_STATE, PWHEA_ERROR_SOURCE_STATE enumeration pointer [WHEA Drivers and Applications], WHEA_ERROR_SOURCE_STATE, WHEA_ERROR_SOURCE_STATE enumeration [WHEA Drivers and Applications], WheaErrSrcStateStarted, WheaErrSrcStateStopped, _WHEA_ERROR_SOURCE_STATE, ntddk/PWHEA_ERROR_SOURCE_STATE, ntddk/WHEA_ERROR_SOURCE_STATE, ntddk/WheaErrSrcStateStarted, ntddk/WheaErrSrcStateStopped, whea.whea_error_source_state, whearef_c6edca73-b5ec-4473-bbe3-9ed5e48f017d.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
-	ntddk.h
api_name:
-	WHEA_ERROR_SOURCE_STATE
product: Windows
targetos: Windows
req.typenames: WHEA_ERROR_SOURCE_STATE, *PWHEA_ERROR_SOURCE_STATE
---

# _WHEA_ERROR_SOURCE_STATE enumeration


## -description


The WHEA_ERROR_SOURCE_STATE enumeration defines the different runtime states for an error source.


## -enum-fields




### -field WheaErrSrcStateStopped

The error source is stopped.


### -field WheaErrSrcStateStarted

The error source is started.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure contains a member of type WHEA_ERROR_SOURCE_STATE that indicates the runtime state of the error source.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560505">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
 

 

