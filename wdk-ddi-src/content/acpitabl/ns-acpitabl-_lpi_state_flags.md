---
UID: NS:acpitabl._LPI_STATE_FLAGS
title: _LPI_STATE_FLAGS
author: windows-driver-content
description: Defines LPI state flags, either as a structure or as an integer.
old-location: acpi\lpi_state_flags.htm
old-project: acpi
ms.assetid: 3A9DECE8-E85A-49D5-8AF1-6C7BA8B1AB7D
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: LPI_STATE_FLAGS, _LPI_STATE_FLAGS, *PLPI_STATE_FLAGS, acpi.lpi_state_flags, acpitabl/LPI_STATE_FLAGS, LPI_STATE_FLAGS union [ACPI Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpitabl.h
req.include-header: Acpitabl.h
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
-	acpitabl.h
apiname: 
-	LPI_STATE_FLAGS
product: Windows
targetos: Windows
req.typenames: LPI_STATE_FLAGS, *PLPI_STATE_FLAGS
---

# _LPI_STATE_FLAGS structure


## -description


Defines LPI state flags, either as a structure or as an integer. 


## -syntax


````
typedef union _LPI_STATE_FLAGS {
  struct  {
        ULONG Disabled:1;
        ULONG CounterUnavailable:1;
        ULONG Reserved:30;
    };
  ULONG  AsUlong;
} LPI_STATE_FLAGS;
````


## -struct-fields




### -field Disabled

 


### -field CounterUnavailable

 


### -field Reserved

 


### -field AsUlong

An LPI state as an integer. 


#### - {
        ULONG Disabled:1;
        ULONG CounterUnavailable:1;
        ULONG Reserved:30;
    }

An LPI state as a structure.

