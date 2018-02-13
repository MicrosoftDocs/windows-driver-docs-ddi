---
UID: NF:wudfddi.IWDFDeviceInitialize.SetLockingConstraint
title: IWDFDeviceInitialize::SetLockingConstraint method
author: windows-driver-content
description: The SetLockingConstraint method sets the synchronization (or locking) model for callback functions into the driver.
old-location: wdf\iwdfdeviceinitialize_setlockingconstraint.htm
old-project: wdf
ms.assetid: c0062ad4-6666-49db-9d53-70f2ed2353d1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: SetLockingConstraint method, SetLockingConstraint method, IWDFDeviceInitialize interface, SetLockingConstraint, UMDFDeviceObjectRef_ec613925-df47-4231-8f53-3769df71f288.xml, IWDFDeviceInitialize interface, SetLockingConstraint method, IWDFDeviceInitialize::SetLockingConstraint, IWDFDeviceInitialize, umdf.iwdfdeviceinitialize_setlockingconstraint, wudfddi/IWDFDeviceInitialize::SetLockingConstraint, wdf.iwdfdeviceinitialize_setlockingconstraint
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDeviceInitialize.SetLockingConstraint
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize::SetLockingConstraint method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetLockingConstraint</b> method sets the synchronization (or locking) model for callback functions into the driver.


## -syntax


````
void SetLockingConstraint(
  [in] WDF_CALLBACK_CONSTRAINT LockType
);
````


## -parameters




### -param LockType [in]

A value of type <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_callback_constraint.md">WDF_CALLBACK_CONSTRAINT</a> that identifies the locking model.


## -returns



This method does not return a value.




## -remarks



The default value of the <i>LockType</i> parameter is <b>WdfDeviceLevel</b>, which is currently the only supported value.


#### Examples

For a code example of how to use the <b>SetLockingConstraint</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>



<a href="..\wudfddi\nn-wudfddi-iwdfdeviceinitialize.md">IWDFDeviceInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::SetLockingConstraint method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

