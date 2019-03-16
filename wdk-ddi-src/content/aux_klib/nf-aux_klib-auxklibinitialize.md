---
UID: NF:aux_klib.AuxKlibInitialize
title: AuxKlibInitialize function (aux_klib.h)
description: The AuxKlibInitialize routine initializes the Auxiliary Kernel-Mode Library.
old-location: kernel\auxklibinitialize.htm
tech.root: kernel
ms.assetid: 7e15cbe1-17f7-4df7-9273-9a365d309d03
ms.date: 04/30/2018
ms.keywords: AuxKlibInitialize, AuxKlibInitialize routine [Kernel-Mode Driver Architecture], aux_klib/AuxKlibInitialize, aux_klib_d83fd3ae-3a26-4798-9ef8-1530adb78543.xml, kernel.auxklibinitialize
ms.topic: function
req.header: aux_klib.h
req.include-header: Aux_klib.h
req.target-type: Universal
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.lib: Aux_Klib.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Aux_Klib.lib
- Aux_Klib.dll
api_name:
- AuxKlibInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# AuxKlibInitialize function


## -description


The <b>AuxKlibInitialize</b> routine initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/aux_klib/">Auxiliary Kernel-Mode Library</a>.


## -parameters






## -returns



<b>AuxKlibInitialize</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the routine returns an appropriate NTSTATUS value.




## -remarks



Drivers that use the Auxiliary Kernel-Mode Library must call <b>AuxKlibInitialize</b> before calling any of the library's other routines.



