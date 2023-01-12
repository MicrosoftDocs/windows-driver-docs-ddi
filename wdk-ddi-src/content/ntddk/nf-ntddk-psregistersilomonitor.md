---
UID: NF:ntddk.PsRegisterSiloMonitor
title: PsRegisterSiloMonitor function (ntddk.h)
description: This routine registers a server silo monitor that can receive notifications about server silo events.
tech.root: kernel
ms.date: 12/07/2022
keywords: ["PsRegisterSiloMonitor function"]
ms.keywords: PsRegisterSiloMonitor, PsRegisterSiloMonitor routine [Kernel-Mode Driver Architecture], kernel.psregistersilomonitor, ntddk/PsRegisterSiloMonitor
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PsRegisterSiloMonitor
 - ntddk/PsRegisterSiloMonitor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsRegisterSiloMonitor
---

## -description

This routine registers a server silo monitor that can receive notifications about server silo events.

To start receiving notifications, call the [PsStartSiloMonitor](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-psstartsilomonitor) routine.

## -parameters

### -param Registration [in]

Specifies the server silo monitor to be registered, of type [**SILO_MONITOR_REGISTRATION**](/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_silo_monitor_registration).

### -param ReturnedMonitor [out]

Receives a pointer to the monitor. This pointer is used to make further monitor-related calls.

## -returns

The following NT status codes are returned:

| Return code | Description |
|---|---|
| **STATUS_INVALID_PARAMETER** | The version specified in **ntddk.h** does not match **SILO_MONITOR_REGISTRATION_VERSION**, the component name is not specified, or the terminate callback is not supplied. |
| **STATUS_PRIVILEDGE_NOT_HELD** | The routine is called in a silo. |
| **STATUS_INSUFFICIENT_RESOURCES** | There is no memory to register a silo monitor or there is no available silo slot. |
| **STATUS_SUCCESS** | The operation completed successfully. |
