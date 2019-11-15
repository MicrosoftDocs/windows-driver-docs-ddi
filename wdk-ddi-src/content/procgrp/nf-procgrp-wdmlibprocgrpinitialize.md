---
UID: NF:procgrp.WdmlibProcgrpInitialize
title: WdmlibProcgrpInitialize function (procgrp.h)
description: The WdmlibProcgrpInitialize function initializes the Processor Group (ProcGrp) compatibility library.
old-location: kernel\wdmlibprocgrpinitialize.htm
tech.root: kernel
ms.assetid: 760f7bd8-0957-4dd0-b201-64173961cbb2
ms.date: 04/30/2018
ms.keywords: WdmlibProcgrpInitialize, WdmlibProcgrpInitialize function [Kernel-Mode Driver Architecture], kernel.wdmlibprocgrpinitialize, procgrp/WdmlibProcgrpInitialize, procgrp_ba92a7bb-1a2b-4056-bebd-d9df299768c1.xml
ms.topic: function
f1_keywords:
 - "procgrp/WdmlibProcgrpInitialize"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Procgrp.lib
- Procgrp.dll
api_name:
- WdmlibProcgrpInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdmlibProcgrpInitialize function


## -description


The <b>WdmlibProcgrpInitialize</b> function initializes the Processor Group (ProcGrp) compatibility library.


## -parameters






## -remarks



This function initializes the ProcGrp library. Call this function before calling any of the other functions in the ProcGrp library. The library implements wrapper functions that have the same names as the following processor-group <b>Ke<i>Xxx</i></b> routines in Windows 7:


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kegetcurrentprocessornumberex">KeGetCurrentProcessorNumberEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-kegetprocessorindexfromnumber">KeGetProcessorIndexFromNumber</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kegetprocessornumberfromindex">KeGetProcessorNumberFromIndex</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryactivegroupcount">KeQueryActiveGroupCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryactiveprocessorcountex">KeQueryActiveProcessorCountEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequerygroupaffinity">KeQueryGroupAffinity</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kequerymaximumprocessorcount">KeQueryMaximumProcessorCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequerymaximumprocessorcountex">KeQueryMaximumProcessorCountEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequerymaximumgroupcount">KeQueryMaximumGroupCount</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemaffinitythreadex">KeSetSystemAffinityThreadEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesetsystemgroupaffinitythread">KeSetSystemGroupAffinityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttouseraffinitythreadex">KeRevertToUserAffinityThreadEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kereverttousergroupaffinitythread">KeRevertToUserGroupAffinityThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-kesettargetprocessordpcex">KeSetTargetProcessorDpcEx</a>


For more information about the ProcGrp library, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Processor Group Compatibility Library</a>. 



