---
UID: NE:dispmprt.__unnamed_enum_0
title: DXGK_SERVICES (dispmprt.h)
description: The DXGK_SERVICES enumeration indicates the type of interface being requested by a call to the DxgkCbQueryServices function.
old-location: display\dxgk_services.htm
tech.root: display
ms.assetid: 8853e0f8-1dd0-4cb5-8dbf-c1d4e62bb0ec
ms.date: 05/10/2018
keywords: ["DXGK_SERVICES enumeration"]
ms.keywords: DXGK_SERVICES, DXGK_SERVICES enumeration [Display Devices], DmEnums_340c8991-c135-47da-876d-2970157fea0b.xml, DxgkServicesAgp, DxgkServicesBDD, DxgkServicesDebugReport, DxgkServicesFirmwareTable, DxgkServicesSPB, DxgkServicesTimedOperation, display.dxgk_services, dispmprt/DXGK_SERVICES, dispmprt/DxgkServicesAgp, dispmprt/DxgkServicesBDD, dispmprt/DxgkServicesDebugReport, dispmprt/DxgkServicesFirmwareTable, dispmprt/DxgkServicesSPB, dispmprt/DxgkServicesTimedOperation
f1_keywords:
 - "dispmprt/DXGK_SERVICES"
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dispmprt.h
api_name:
- DXGK_SERVICES
product:
- Windows
targetos: Windows
req.typenames: DXGK_SERVICES
---

# DXGK_SERVICES enumeration


## -description


The DXGK_SERVICES enumeration indicates the type of interface being requested by a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_query_services">DxgkCbQueryServices</a> function.


## -enum-fields




### -field DxgkServicesAgp

Indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">AGP Interface</a>.


### -field DxgkServicesDebugReport

Indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Debug Report interface</a>.


### -field DxgkServicesTimedOperation

Indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Timed Operation interface</a>.


### -field DxgkServicesSPB

Indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Simple  Peripheral Bus (SPB) Interface</a>.

Supported starting with Windows 8.


### -field DxgkServicesBDD

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.


### -field DxgkServicesFirmwareTable

Indicates the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_firmware_table_interface">System Firmware Table Interface</a>.

Supported starting with Windows 8.


### -field DxgkServicesIDD




## -remarks



An interface, in this context, is a set of function pointers. The functions in the AGP, Debug Report, Timed Operation, SPB, and System Firmware Table interfaces are implemented by the Microsoft DirectX graphics kernel subsystem and called by the display miniport driver.



