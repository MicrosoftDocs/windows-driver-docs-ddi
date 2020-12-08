---
UID: NF:pepfx.PoFxRegisterPlugin
title: PoFxRegisterPlugin function (pepfx.h)
description: The PoFxRegisterPlugin routine registers a platform extension plug-in (PEP) with the Windows power management framework (PoFx).
old-location: kernel\pofxregisterplugin.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PoFxRegisterPlugin function"]
ms.keywords: PoFxRegisterPlugin, PoFxRegisterPlugin routine [Kernel-Mode Driver Architecture], kernel.pofxregisterplugin, pepfx/PoFxRegisterPlugin
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PoFxRegisterPlugin
 - pepfx/PoFxRegisterPlugin
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
---

# PoFxRegisterPlugin function (pepfx.h)


## -description

The **PoFxRegisterPlugin** routine registers a platform extension plug-in (PEP) with the Windows [power management framework](/windows-hardware/drivers/kernel/overview-of-the-power-management-framework) (PoFx).

## -parameters

### -param PepInformation 

[in]
A pointer to a [PEP_INFORMATION](./ns-pepfx-_pep_information.md) structure.

### -param KernelInformation 

[in, out]
A pointer to a [PEP_KERNEL_INFORMATION_STRUCT_V3](./ns-pepfx-_pep_kernel_information_struct_v3.md) structure.

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

The [PoFxRegisterPluginEx](./nf-pepfx-pofxregisterpluginex.md) routine is similar to **PoFxRegisterPlugin**, except that it takes an additional parameter, *Flags*.

The PEP must call **PoFxRegisterPlugin** at IRQL = PASSIVE_LEVEL.

## -see-also

[PEP_INFORMATION](./ns-pepfx-_pep_information.md)

[PEP_KERNEL_INFORMATION_STRUCT_V3](./ns-pepfx-_pep_kernel_information_struct_v3.md)

[PoFxRegisterPluginEx](./nf-pepfx-pofxregisterpluginex.md)
