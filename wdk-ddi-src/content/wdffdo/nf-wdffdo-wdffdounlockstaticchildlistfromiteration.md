---
UID: NF:wdffdo.WdfFdoUnlockStaticChildListFromIteration
title: WdfFdoUnlockStaticChildListFromIteration function (wdffdo.h)
description: The WdfFdoUnlockStaticChildListFromIteration method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked.
old-location: wdf\wdffdounlockstaticchildlistfromiteration.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfFdoUnlockStaticChildListFromIteration function"]
ms.keywords: DFDeviceObjectFdoPdoRef_5d630e1f-4c2d-4fce-92d8-c59cc472ceb5.xml, WdfFdoUnlockStaticChildListFromIteration, WdfFdoUnlockStaticChildListFromIteration method, kmdf.wdffdounlockstaticchildlistfromiteration, wdf.wdffdounlockstaticchildlistfromiteration, wdffdo/WdfFdoUnlockStaticChildListFromIteration
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfFdoUnlockStaticChildListFromIteration
 - wdffdo/WdfFdoUnlockStaticChildListFromIteration
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfFdoUnlockStaticChildListFromIteration
---

# WdfFdoUnlockStaticChildListFromIteration function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfFdoUnlockStaticChildListFromIteration</b> method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked.

## -parameters

### -param Fdo 

[in]
A handle to a framework device object that represents the parent device.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




Bus drivers that use static bus enumeration can call <b>WdfFdoUnlockStaticChildListFromIteration</b>. 

To lock a child list, the driver calls <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdolockstaticchildlistforiteration">WdfFdoLockStaticChildListForIteration</a>. 

Calls to <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdolockstaticchildlistforiteration">WdfFdoLockStaticChildListForIteration</a> can be nested and must be matched by an equal number of calls to <b>WdfFdoUnlockStaticChildListFromIteration</b>. If a driver adds or removes items from the child list while it is locked, the framework queues these changes and processes them after the last call to <b>WdfFdoUnlockStaticChildListFromIteration</b>.

For more information about static child lists, see <a href="/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

For a code example that uses <b>WdfFdoUnlockStaticChildListFromIteration</b>, see <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoretrievenextstaticchild">WdfFdoRetrieveNextStaticChild</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdolockstaticchildlistforiteration">WdfFdoLockStaticChildListForIteration</a>
