---
UID: NF:pepfx.PoFxRegisterPlugin
title: PoFxRegisterPlugin function (pepfx.h)
description: The PoFxRegisterPlugin routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx).
old-location: kernel\pofxregisterplugin.htm
tech.root: kernel
ms.assetid: BB50112E-6706-419C-9686-79F0F76926C3
ms.date: 04/30/2018
ms.keywords: PoFxRegisterPlugin, PoFxRegisterPlugin routine [Kernel-Mode Driver Architecture], kernel.pofxregisterplugin, pepfx/PoFxRegisterPlugin
f1_keywords:
 - "pepfx/PoFxRegisterPlugin"
req.header: pepfx.h
req.include-header: Pep_x.h
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ntoskrnl.lib
- ntoskrnl.dll
api_name:
- PoFxRegisterPlugin
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxRegisterPlugin function

## -description

The **PoFxRegisterPlugin** routine registers a platform extension plug-in (PEP) with the Windows [power management framework](https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) (PoFx).

## -parameters

### -param PepInformation [in]

A pointer to a [PEP_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_information) structure.

### -param KernelInformation [in, out]

A pointer to a [PEP_KERNEL_INFORMATION_STRUCT_V3](https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3) structure.

## -returns

**PoFxRegisterPlugin** returns STATUS_SUCCESS if the call successfully registers the PEP. Possible error return values include the following status codes.

|Return value|Description|
|----|----|
|STATUS_INVALID_PARAMETER|The **Version** or **Size** member of the **PEP_KERNEL_INFORMATION** structure is set to an invalid value; or the **AcceptDeviceNotification** member of this structure is set to NULL.|
|STATUS_INVALID_PEP_INFO_VERSION|The **Version** member of the **PEP_INFORMATION** structure is set to an invalid value.|
|STATUS_INSUFFICIENT_RESOURCES|Unable to allocate the resources required to complete the requested registration.|

## -remarks

A PEP calls this routine to register itself with PoFx.

A PEP cannot unregister, and cannot register twice. If the PEP must be serviced, the operating system must restart.

The [PoFxRegisterPluginEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex) routine is similar to **PoFxRegisterPlugin**, except that it takes an additional parameter, *Flags*.

The PEP must call **PoFxRegisterPlugin** at IRQL = PASSIVE_LEVEL.

## -see-also

[PEP_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_information)

[PEP_KERNEL_INFORMATION_STRUCT_V3](https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3)

[PoFxRegisterPluginEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex)
