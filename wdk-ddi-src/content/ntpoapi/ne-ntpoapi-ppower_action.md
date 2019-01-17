---
UID: NE:ntpoapi.__unnamed_enum_0
title: "*PPOWER_ACTION"
description: The POWER_ACTION enumeration identifies the system power actions that can occur on a computer.
old-location: wdf\power_action.htm
tech.root: kernel
ms.assetid: 0c4a5eb8-d364-4e5d-9d2f-2605c8c34f63
ms.date: 02/26/2018
ms.keywords: "*PPOWER_ACTION, POWER_ACTION, POWER_ACTION enumeration, PPOWER_ACTION, PPOWER_ACTION enumeration pointer, PowerActionHibernate, PowerActionNone, PowerActionReserved, PowerActionShutdown, PowerActionShutdownOff, PowerActionShutdownReset, PowerActionSleep, PowerActionWarmEject, umdf.power_action, umdfstructs_02db2a83-1907-4aa2-9cdd-af3477e78ddd.xml, wdf.power_action, wudfddi/POWER_ACTION, wudfddi/PPOWER_ACTION, wudfddi/PowerActionHibernate, wudfddi/PowerActionNone, wudfddi/PowerActionReserved, wudfddi/PowerActionShutdown, wudfddi/PowerActionShutdownOff, wudfddi/PowerActionShutdownReset, wudfddi/PowerActionSleep, wudfddi/PowerActionWarmEject"
ms.topic: enum
req.header: ntpoapi.h
req.include-header: Wudfddi.h, Ntpoapi.h, Wdm.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver: 1.9
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi.h
api_name:
-	POWER_ACTION
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
---

# *PPOWER_ACTION enumeration


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>POWER_ACTION</b> enumeration identifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564553">system power actions</a> that can occur on a computer.


## -syntax


```cpp
typedef enum  {
  PowerActionNone           = 0,
  PowerActionReserved       = ( PowerActionNone + 1 ),
  PowerActionSleep          = ( PowerActionReserved + 1 ),
  PowerActionHibernate      = ( PowerActionSleep + 1 ),
  PowerActionShutdown       = ( PowerActionHibernate + 1 ),
  PowerActionShutdownReset  = ( PowerActionShutdown + 1 ),
  PowerActionShutdownOff    = ( PowerActionShutdownReset + 1 ),
  PowerActionWarmEject      = ( PowerActionShutdownOff + 1 )
} POWER_ACTION, *PPOWER_ACTION;
```


## -enum-fields




### -field PowerActionNone

No power action is taking place.


### -field PowerActionReserved

Reserved for system use.


### -field PowerActionSleep

The computer is entering a <a href="https://msdn.microsoft.com/2fd883b5-4e89-4ce9-b75a-b821348ac860">system sleeping (S1, S2, or S3) state</a>.


### -field PowerActionHibernate

The computer is entering its <a href="https://msdn.microsoft.com/2fd883b5-4e89-4ce9-b75a-b821348ac860">hibernation (S4) state</a>.


### -field PowerActionShutdown

The computer is entering its <a href="https://msdn.microsoft.com/c08d688d-c31a-4d57-a343-406edfa35e8f">shutdown (S5) state</a>. After all devices have entered their <a href="https://msdn.microsoft.com/f594a63f-10ce-439d-abe3-d342555d98f0">off (D3) state</a>, the computer remains powered on until an administrator presses the power button.


### -field PowerActionShutdownReset

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off and then immediately restarts and returns to its working (S0) state.


### -field PowerActionShutdownOff

The computer is entering its shutdown (S5) state. After all devices have entered their off (D3) state, the computer automatically powers off.


### -field PowerActionWarmEject

The computer is being ejected from an ACPI-compatible dock device. Typically, the computer's power state does not change.


### -field PowerActionDisplayOff




## -remarks



The <b>POWER_ACTION</b> enumeration is used as the return value for <a href="https://msdn.microsoft.com/library/windows/hardware/ff556936">IWDFDevice2::GetSystemPowerAction</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556936">IWDFDevice2::GetSystemPowerAction</a>



 

 


