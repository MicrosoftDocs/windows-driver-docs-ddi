---
UID: NS:pepfx._PEP_COORDINATED_IDLE_STATE
title: _PEP_COORDINATED_IDLE_STATE
author: windows-driver-content
description: The PEP_COORIDNATED_IDLE_STATE structure describes a coordinated idle state to the OS.
old-location: kernel\pep_coordinated_idle_state.htm
old-project: kernel
ms.assetid: 0B3B53F8-2D1E-430B-9C51-E35465899811
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_COORDINATED_IDLE_STATE, PEP_COORDINATED_IDLE_STATE, *PPEP_COORDINATED_IDLE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_COORDINATED_IDLE_STATE
req.alt-loc: pepfx.h
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
req.typenames: PEP_COORDINATED_IDLE_STATE, *PPEP_COORDINATED_IDLE_STATE
---

# _PEP_COORDINATED_IDLE_STATE structure



## -description
The <b>PEP_COORIDNATED_IDLE_STATE</b> structure describes a coordinated idle state to the OS.



## -syntax

````
typedef struct _PEP_COORDINATED_IDLE_STATE {
  ULONG Latency;
  ULONG BreakEvenDuration;
  ULONG DependencyCount;
  ULONG MaximumDependencySize;
} PEP_COORDINATED_IDLE_STATE, *PPEP_COORDINATED_IDLE_STATE;
````


## -struct-fields

### -field Latency

The latency of waking from this idle state, in 100ns units.


### -field BreakEvenDuration

Supplies the minimum time the state must be entered to amortize the cost of entering/exiting the state. Idle durations longer than this period should save power when compared to entering a lighter state for the same period.


### -field DependencyCount

Supplies the number of dependencies this coordinated state has on other coordinated states or on processors.


### -field MaximumDependencySize

Supplies the maximum size of a single dependency.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt186776">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATES notification</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_coordinated_idle_state.md">PEP_COORDINATED_IDLE_STATE structure</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COORDINATED_IDLE_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

