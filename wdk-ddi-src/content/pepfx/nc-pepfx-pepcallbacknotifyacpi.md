---
UID: NC:pepfx.PEPCALLBACKNOTIFYACPI
title: PEPCALLBACKNOTIFYACPI (pepfx.h)
description: An AcceptAcpiNotification event callback routine handles ACPI notifications from the Windows power management framework (PoFx).
old-location: kernel\acceptacpinotification.htm
tech.root: kernel
ms.assetid: 7BC27FD1-CCD8-4ABC-B973-C2242D6C243B
ms.date: 04/30/2018
keywords: ["PEPCALLBACKNOTIFYACPI callback function"]
ms.keywords: AcceptAcpiNotification, AcceptAcpiNotification routine [Kernel-Mode Driver Architecture], PEPCALLBACKNOTIFYACPI, kernel.acceptacpinotification, pepfx/AcceptAcpiNotification
req.header: pepfx.h
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
req.irql: <= HIGH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PEPCALLBACKNOTIFYACPI
 - pepfx/PEPCALLBACKNOTIFYACPI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - pepfx.h
api_name:
 - AcceptAcpiNotification
---

# PEPCALLBACKNOTIFYACPI callback function (pepfx.h)


## -description

An <i>AcceptAcpiNotification</i> event callback routine handles ACPI notifications from the Windows <a href="/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).

## -parameters

### -param Notification 

[in]
The ACPI notification ID. This parameter specifies the type of ACPI notification that PoFx is sending. For a list of ACPI notification IDs, see <a href="/windows-hardware/drivers/kernel/acpi-notifications">ACPI notifications</a>.

### -param Data 

[in, out, optional]
A pointer to a PoFx-allocated structure that contains the input and/or output data for this notification. The type of this structure depends on the notification ID specified by <i>Notification</i>. For a list of the structure types that are defined for the various ACPI notification IDs, see <a href="/windows-hardware/drivers/ddi/index">ACPI notifications</a>.

## -returns

The <i>AcceptAcpiNotification</i> routine must return TRUE if it handles the notification, or FALSE if it does not.

## -remarks

This routine is implemented by the platform extension plug-in (PEP) for a device. The <b>AcceptAcpiNotification</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_information">PEP_INFORMATION</a> structure is a pointer to an <i>AcceptAcpiNotification</i> routine. The PEP calls the <a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a> or <a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a> routine to register the PEP's <i>AcceptAcpiNotification</i> routine with PoFx.

The IRQL at which the PEP's <i>AcceptAcpiNotification</i> routine is called varies according to the type of notification that is being sent. The notification type is specified by the <i>Notification</i> parameter. For more information about the IRQL at which each notification type is sent, see the individual reference pages under <a href="/windows-hardware/drivers/ddi/index">ACPI notifications</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_information">PEP_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterplugin">PoFxRegisterPlugin</a>



<a href="/windows-hardware/drivers/ddi/pepfx/nf-pepfx-pofxregisterpluginex">PoFxRegisterPluginEx</a>