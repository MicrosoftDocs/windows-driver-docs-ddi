---
UID: NF:procgrp.WdmlibProcgrpInitialize
title: WdmlibProcgrpInitialize function
author: windows-driver-content
description: The WdmlibProcgrpInitialize function initializes the Processor Group (ProcGrp) compatibility library.
old-location: kernel\wdmlibprocgrpinitialize.htm
old-project: kernel
ms.assetid: 760f7bd8-0957-4dd0-b201-64173961cbb2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: WdmlibProcgrpInitialize, WdmlibProcgrpInitialize function [Kernel-Mode Driver Architecture], kernel.wdmlibprocgrpinitialize, procgrp/WdmlibProcgrpInitialize, procgrp_ba92a7bb-1a2b-4056-bebd-d9df299768c1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: procgrp.h
req.include-header: Procgrp.h
req.target-type: Desktop
req.target-min-winverclnt: Compatible with Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, Windows Server 2003, Windows XP, and Windows 2000.
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
req.lib: Procgrp.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Procgrp.lib
-	Procgrp.dll
api_name:
-	WdmlibProcgrpInitialize
product: Windows
targetos: Windows
req.typenames: WIDTHTABLE, *PWIDTHTABLE
req.product: Windows 10 or later.
---

# WdmlibProcgrpInitialize function


## -description


The <b>WdmlibProcgrpInitialize</b> function initializes the Processor Group (ProcGrp) compatibility library.


## -parameters






## -returns



None




## -remarks



This function initializes the ProcGrp library. Call this function before calling any of the other functions in the ProcGrp library. The library implements wrapper functions that have the same names as the following processor-group <b>Ke<i>Xxx</i></b> routines in Windows 7:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff552076">KeGetCurrentProcessorNumberEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552096">KeGetProcessorIndexFromNumber</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552100">KeGetProcessorNumberFromIndex</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552981">KeQueryActiveGroupCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552993">KeQueryActiveProcessorCountEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553007">KeQueryGroupAffinity</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553042">KeQueryMaximumProcessorCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553044">KeQueryMaximumProcessorCountEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553035">KeQueryMaximumGroupCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553271">KeSetSystemAffinityThreadEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553275">KeSetSystemGroupAffinityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553190">KeRevertToUserAffinityThreadEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553195">KeRevertToUserGroupAffinityThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553279">KeSetTargetProcessorDpcEx</a>


For more information about the ProcGrp library, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559909">Processor Group Compatibility Library</a>. 



