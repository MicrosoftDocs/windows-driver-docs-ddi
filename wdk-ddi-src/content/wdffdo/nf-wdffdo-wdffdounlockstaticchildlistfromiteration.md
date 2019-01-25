---
UID: NF:wdffdo.WdfFdoUnlockStaticChildListFromIteration
title: WdfFdoUnlockStaticChildListFromIteration function (wdffdo.h)
description: The WdfFdoUnlockStaticChildListFromIteration method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked.
old-location: wdf\wdffdounlockstaticchildlistfromiteration.htm
tech.root: wdf
ms.assetid: ba0eb090-a03c-4723-a30c-16b161e50198
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_5d630e1f-4c2d-4fce-92d8-c59cc472ceb5.xml, WdfFdoUnlockStaticChildListFromIteration, WdfFdoUnlockStaticChildListFromIteration method, kmdf.wdffdounlockstaticchildlistfromiteration, wdf.wdffdounlockstaticchildlistfromiteration, wdffdo/WdfFdoUnlockStaticChildListFromIteration
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfFdoUnlockStaticChildListFromIteration
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFdoUnlockStaticChildListFromIteration function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoUnlockStaticChildListFromIteration</b> method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked. 


## -parameters




### -param Fdo [in]

A handle to a framework device object that represents the parent device.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Bus drivers that use static bus enumeration can call <b>WdfFdoUnlockStaticChildListFromIteration</b>. 

To lock a child list, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a>. 

Calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a> can be nested and must be matched by an equal number of calls to <b>WdfFdoUnlockStaticChildListFromIteration</b>. If a driver adds or removes items from the child list while it is locked, the framework queues these changes and processes them after the last call to <b>WdfFdoUnlockStaticChildListFromIteration</b>.

For more information about static child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

For a code example that uses <b>WdfFdoUnlockStaticChildListFromIteration</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547293">WdfFdoRetrieveNextStaticChild</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a>
 

 

