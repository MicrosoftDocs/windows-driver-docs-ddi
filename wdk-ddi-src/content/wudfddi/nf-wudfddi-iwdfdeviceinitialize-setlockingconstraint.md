---
UID: NF:wudfddi.IWDFDeviceInitialize.SetLockingConstraint
title: IWDFDeviceInitialize::SetLockingConstraint (wudfddi.h)
description: The SetLockingConstraint method sets the synchronization (or locking) model for callback functions into the driver.
old-location: wdf\iwdfdeviceinitialize_setlockingconstraint.htm
tech.root: wdf
ms.assetid: c0062ad4-6666-49db-9d53-70f2ed2353d1
ms.date: 02/26/2018
ms.keywords: IWDFDeviceInitialize interface,SetLockingConstraint method, IWDFDeviceInitialize.SetLockingConstraint, IWDFDeviceInitialize::SetLockingConstraint, SetLockingConstraint, SetLockingConstraint method, SetLockingConstraint method,IWDFDeviceInitialize interface, UMDFDeviceObjectRef_ec613925-df47-4231-8f53-3769df71f288.xml, umdf.iwdfdeviceinitialize_setlockingconstraint, wdf.iwdfdeviceinitialize_setlockingconstraint, wudfddi/IWDFDeviceInitialize::SetLockingConstraint
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDeviceInitialize.SetLockingConstraint
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFDeviceInitialize::SetLockingConstraint


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetLockingConstraint</b> method sets the synchronization (or locking) model for callback functions into the driver.


## -parameters




### -param LockType [in]

A value of type <a href="https://msdn.microsoft.com/118a9dcc-8dd4-454a-bab2-1558821781a7">WDF_CALLBACK_CONSTRAINT</a> that identifies the locking model.


## -returns



This method does not return a value.




## -remarks



The default value of the <i>LockType</i> parameter is <b>WdfDeviceLevel</b>, which is currently the only supported value.


#### Examples

For a code example of how to use the <b>SetLockingConstraint</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556965">IWDFDeviceInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>
 

 

