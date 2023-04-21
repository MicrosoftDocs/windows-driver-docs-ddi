---
UID: NC:ntddk.PSHED_PI_GET_INJECTION_CAPABILITIES
title: PSHED_PI_GET_INJECTION_CAPABILITIES (ntddk.h)
description: A PSHED plug-in's GetInjectionCapabilities callback function returns an error injection capabilities union that describes the types of hardware errors that can be injected into the hardware platform.
tech.root: whea
ms.date: 04/17/2023
keywords: ["PSHED_PI_GET_INJECTION_CAPABILITIES callback function"]
ms.keywords: GetInjectionCapabilities, GetInjectionCapabilities callback function [WHEA Drivers and Applications], PSHED_PI_GET_INJECTION_CAPABILITIES, PSHED_PI_GET_INJECTION_CAPABILITIES callback, ntddk/GetInjectionCapabilities, whea.getinjectioncapabilities, whearef_0c5e00c7-c5d7-4e28-a351-7831d883c70f.xml
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Desktop
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
req.irql: IRQL = DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PSHED_PI_GET_INJECTION_CAPABILITIES
 - ntddk/PSHED_PI_GET_INJECTION_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ntddk.h
api_name:
 - PSHED_PI_GET_INJECTION_CAPABILITIES
---

## -description

A PSHED plug-in's *GetInjectionCapabilities* callback function returns an error injection capabilities union that describes the types of hardware errors that can be injected into the hardware platform.

## -parameters

### -param PluginContext [in, out, optional]

A pointer to the context area that was specified in the **Context** member of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure when the PSHED plug-in called the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED.

### -param Capabilities [out]

A pointer to a [**WHEA_ERROR_INJECTION_CAPABILITIES**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_injection_capabilities) union. This union receives the data that describes the types of hardware errors that can be injected into the hardware platform.

## -returns

A PSHED plug-in's *GetInjectionCapabilities* callback function returns one of the following NTSTATUS codes:

| Return code | Description |
|--|--|
| **STATUS_SUCCESS** | The data that describes the types of hardware errors that can be injected into the hardware platform was successfully returned in the **WHEA_ERROR_INJECTION_CAPABILITIES** union pointed to by the *Capabilities* parameter. |
| **STATUS_UNSUCCESSFUL** | An error occurred. |

## -remarks

A PSHED plug-in that participates in error injection sets the **Callbacks.GetInjectionCapabilities** and **Callbacks.InjectError** members of the [**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet) structure to point to its *GetInjectionCapabilities* and [InjectError](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_inject_error) callback functions when the plug-in calls the [PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin) function to register itself with the PSHED. The PSHED plug-in must also set the **PshedFAErrorInjection** flag in the **FunctionalAreaMask** member of the **WHEA_PSHED_PLUGIN_REGISTRATION_PACKET** structure.

The Windows kernel calls into the PSHED to retrieve information about the types of hardware errors that can be injected into the hardware platform in response to an error injection capabilities inquiry by a WHEA management application. If a PSHED plug-in is registered to participate in error injection, the PSHED calls the PSHED plug-in's *GetInjectionCapabilities* callback function to retrieve information about additional types of hardware errors that can be injected into the hardware platform.

## -see-also

[InjectError](/windows-hardware/drivers/ddi/ntddk/nc-ntddk-pshed_pi_inject_error)

[PshedRegisterPlugin](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pshedregisterplugin)

[**WHEA_ERROR_INJECTION_CAPABILITIES**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_error_injection_capabilities)

[**WHEA_PSHED_PLUGIN_REGISTRATION_PACKET**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_registration_packet)
