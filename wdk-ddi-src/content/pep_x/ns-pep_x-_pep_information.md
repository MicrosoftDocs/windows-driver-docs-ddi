---
UID: NS:pep_x._PEP_INFORMATION
title: _PEP_INFORMATION (pep_x.h)
description: The PEP_INFORMATION structure specifies the interface that the platform extension plug-in (PEP) uses to receive notifications from the Windows power management framework (PoFx).
old-location: kernel\pep_information.htm
tech.root: kernel
ms.assetid: 60221D44-79C0-4043-A4AF-1200C2F087F6
ms.date: 04/30/2018
ms.keywords: "*PPEP_INFORMATION, PEP_INFORMATION, PEP_INFORMATION structure [Kernel-Mode Driver Architecture], PPEP_INFORMATION, PPEP_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _PEP_INFORMATION, kernel.pep_information, pepfx/PEP_INFORMATION, pepfx/PPEP_INFORMATION"
ms.topic: struct
f1_keywords:
 - "pep_x/PEP_INFORMATION"
req.header: pep_x.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PEP_INFORMATION, *PPEP_INFORMATION
---

# _PEP_INFORMATION structure


## -description


The <b>PEP_INFORMATION</b> structure specifies the interface that the platform extension plug-in (PEP) uses to receive notifications from the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).


## -struct-fields




### -field Version

The current version number for this structure. Set this member to PEP_INFORMATION_VERSION.


### -field Size

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>PEP_INFORMATION</b>).


### -field AcceptDeviceNotification

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbacknotifydpm">AcceptDeviceNotification</a> callback routine. This member is required to point to a valid callback routine.


### -field AcceptProcessorNotification

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbacknotifyppm">AcceptProcessorNotification</a> callback routine. This member is optional and can be NULL if the PEP is not prepared to handle PPM notifications from PoFx.


### -field AcceptAcpiNotification

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbacknotifyacpi">AcceptAcpiNotification</a> callback routine. This member is optional and can be NULL if the PEP is not prepared to handle ACPI notifications from PoFx.


## -remarks



This structure contains pointers to several callback routines that are implemented by the PEP. PoFx calls these routines to send notifications to the PEP.

The <i>PepInformation</i> parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a> routines is a pointer to a <b>PEP_INFORMATION</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbacknotifyacpi">AcceptAcpiNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbacknotifydpm">AcceptDeviceNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pepcallbacknotifyppm">AcceptProcessorNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a>
 

 

