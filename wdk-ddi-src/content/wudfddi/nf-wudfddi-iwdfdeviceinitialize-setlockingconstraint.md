---
UID: NF:wudfddi.IWDFDeviceInitialize.SetLockingConstraint
title: IWDFDeviceInitialize::SetLockingConstraint (wudfddi.h)
description: The SetLockingConstraint method sets the synchronization (or locking) model for callback functions into the driver.
old-location: wdf\iwdfdeviceinitialize_setlockingconstraint.htm
tech.root: wdf
ms.assetid: c0062ad4-6666-49db-9d53-70f2ed2353d1
ms.date: 02/26/2018
keywords: ["IWDFDeviceInitialize::SetLockingConstraint"]
ms.keywords: IWDFDeviceInitialize interface,SetLockingConstraint method, IWDFDeviceInitialize.SetLockingConstraint, IWDFDeviceInitialize::SetLockingConstraint, SetLockingConstraint, SetLockingConstraint method, SetLockingConstraint method,IWDFDeviceInitialize interface, UMDFDeviceObjectRef_ec613925-df47-4231-8f53-3769df71f288.xml, umdf.iwdfdeviceinitialize_setlockingconstraint, wdf.iwdfdeviceinitialize_setlockingconstraint, wudfddi/IWDFDeviceInitialize::SetLockingConstraint
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFDeviceInitialize::SetLockingConstraint
 - wudfddi/IWDFDeviceInitialize::SetLockingConstraint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFDeviceInitialize.SetLockingConstraint
---

# IWDFDeviceInitialize::SetLockingConstraint


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>SetLockingConstraint</b> method sets the synchronization (or locking) model for callback functions into the driver.

## -parameters

### -param LockType 

[in]
A value of type <a href="/windows-hardware/drivers/ddi/wudfddi_types/ne-wudfddi_types-_wdf_callback_constraint">WDF_CALLBACK_CONSTRAINT</a> that identifies the locking model.

## -remarks

The default value of the <i>LockType</i> parameter is <b>WdfDeviceLevel</b>, which is currently the only supported value.


#### Examples

For a code example of how to use the <b>SetLockingConstraint</b> method, see <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdeviceinitialize">IWDFDeviceInitialize</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>