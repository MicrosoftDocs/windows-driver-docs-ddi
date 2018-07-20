---
UID: NE:d3dkmdt._D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT
title: "_D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT"
author: windows-driver-content
description: The D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT enumeration is used to indicate the type of constraint under which a monitor frequency range is supported.
old-location: display\d3dkmdt_monitor_frequency_range_constraint.htm
tech.root: display
ms.assetid: 12bf26fc-86c2-4b9b-82d4-1e8b2e38fa79
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMDT_MFRC_ACTIVESIZE, D3DKMDT_MFRC_MAXPIXELRATE, D3DKMDT_MFRC_UNINITIALIZED, D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT, D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT enumeration [Display Devices], DmEnums_923a6c46-3d71-4d26-8f28-2bf5c6f4bd32.xml, _D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT, d3dkmdt/D3DKMDT_MFRC_ACTIVESIZE, d3dkmdt/D3DKMDT_MFRC_MAXPIXELRATE, d3dkmdt/D3DKMDT_MFRC_UNINITIALIZED, d3dkmdt/D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT, display.d3dkmdt_monitor_frequency_range_constraint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmdt.h
api_name:
-	D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT
---

# _D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT enumeration


## -description


The D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT enumeration is used to indicate the type of constraint under which a monitor frequency range is supported.


## -enum-fields




### -field D3DKMDT_MFRC_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT has not yet been assigned a meaningful value.


### -field D3DKMDT_MFRC_ACTIVESIZE

Indicates that the constraint is an active region size.


### -field D3DKMDT_MFRC_MAXPIXELRATE

Indicates that the constraint is a pixel rate.


## -remarks



The <b>ConstraintType</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546103">D3DKMDT_MONITOR_FREQUENCY_RANGE</a> structure is a value from the D3DKMDT_MONITOR_FREQUENCY_RANGE_CONSTRAINT enumeration.



