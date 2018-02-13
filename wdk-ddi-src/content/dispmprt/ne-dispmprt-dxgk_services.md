---
UID: NE:dispmprt.DXGK_SERVICES
title: DXGK_SERVICES
author: windows-driver-content
description: The DXGK_SERVICES enumeration indicates the type of interface being requested by a call to the DxgkCbQueryServices function.
old-location: display\dxgk_services.htm
old-project: display
ms.assetid: 8853e0f8-1dd0-4cb5-8dbf-c1d4e62bb0ec
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DxgkServicesFirmwareTable, dispmprt/DxgkServicesBDD, dispmprt/DXGK_SERVICES, DxgkServicesDebugReport, dispmprt/DxgkServicesAgp, dispmprt/DxgkServicesTimedOperation, DXGK_SERVICES, dispmprt/DxgkServicesSPB, DxgkServicesTimedOperation, DmEnums_340c8991-c135-47da-876d-2970157fea0b.xml, display.dxgk_services, DxgkServicesAgp, DxgkServicesSPB, dispmprt/DxgkServicesFirmwareTable, DXGK_SERVICES enumeration [Display Devices], DxgkServicesBDD, dispmprt/DxgkServicesDebugReport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DXGK_SERVICES
product: Windows
targetos: Windows
req.typenames: DXGK_SERVICES
---

# DXGK_SERVICES enumeration


## -description


The DXGK_SERVICES enumeration indicates the type of interface being requested by a call to the <a href="..\dispmprt\nc-dispmprt-dxgkcb_query_services.md">DxgkCbQueryServices</a> function.


## -syntax


````
typedef enum  { 
  DxgkServicesAgp             = 0,
  DxgkServicesDebugReport     = 1,
  DxgkServicesTimedOperation  = 2,
  DxgkServicesSPB             = 3,
  DxgkServicesBDD             = 4,
  DxgkServicesFirmwareTable   = 4
} DXGK_SERVICES;
````


## -enum-fields




### -field DxgkServicesAgp

Indicates the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538228">AGP Interface</a>.


### -field DxgkServicesDebugReport

Indicates the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551798">Debug Report interface</a>.


### -field DxgkServicesTimedOperation

Indicates the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570086">Timed Operation interface</a>.


### -field DxgkServicesSPB

Indicates the <a href="https://msdn.microsoft.com/D525A961-339D-414B-B40F-14AD9AEA51C5">Simple  Peripheral Bus (SPB) Interface</a>.

Supported starting with Windows 8.


### -field DxgkServicesBDD

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.


### -field DxgkServicesFirmwareTable

Indicates the <a href="https://msdn.microsoft.com/library/windows/hardware/jj647606">System Firmware Table Interface</a>.

Supported starting with Windows 8.


### -field DxgkServicesIDD




## -remarks



An interface, in this context, is a set of function pointers. The functions in the AGP, Debug Report, Timed Operation, SPB, and System Firmware Table interfaces are implemented by the Microsoft DirectX graphics kernel subsystem and called by the display miniport driver.



