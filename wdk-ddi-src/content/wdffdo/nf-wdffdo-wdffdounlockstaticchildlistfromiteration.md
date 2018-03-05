---
UID: NF:wdffdo.WdfFdoUnlockStaticChildListFromIteration
title: WdfFdoUnlockStaticChildListFromIteration function
author: windows-driver-content
description: The WdfFdoUnlockStaticChildListFromIteration method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked.
old-location: wdf\wdffdounlockstaticchildlistfromiteration.htm
old-project: wdf
ms.assetid: ba0eb090-a03c-4723-a30c-16b161e50198
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_5d630e1f-4c2d-4fce-92d8-c59cc472ceb5.xml, WdfFdoUnlockStaticChildListFromIteration, WdfFdoUnlockStaticChildListFromIteration method, kmdf.wdffdounlockstaticchildlistfromiteration, wdf.wdffdounlockstaticchildlistfromiteration, wdffdo/WdfFdoUnlockStaticChildListFromIteration
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoUnlockStaticChildListFromIteration function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoUnlockStaticChildListFromIteration</b> method unlocks the list of child devices for a specified device and processes any changes to the list that the driver made while the list was locked. 


## -syntax


````
VOID WdfFdoUnlockStaticChildListFromIteration(
  _In_ WDFDEVICE Fdo
);
````


## -parameters




### -param Fdo [in]

A handle to a framework device object that represents the parent device.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Bus drivers that use static bus enumeration can call <b>WdfFdoUnlockStaticChildListFromIteration</b>. 

To lock a child list, the driver calls <a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a>. 

Calls to <a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a> can be nested and must be matched by an equal number of calls to <b>WdfFdoUnlockStaticChildListFromIteration</b>. If a driver adds or removes items from the child list while it is locked, the framework queues these changes and processes them after the last call to <b>WdfFdoUnlockStaticChildListFromIteration</b>.

For more information about static child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

For a code example that uses <b>WdfFdoUnlockStaticChildListFromIteration</b>, see <a href="..\wdffdo\nf-wdffdo-wdffdoretrievenextstaticchild.md">WdfFdoRetrieveNextStaticChild</a>.

<div class="code"></div>



## -see-also

<a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoUnlockStaticChildListFromIteration method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

