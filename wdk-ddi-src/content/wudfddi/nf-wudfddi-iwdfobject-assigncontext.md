---
UID: NF:wudfddi.IWDFObject.AssignContext
title: IWDFObject::AssignContext (wudfddi.h)
description: The AssignContext method registers a context and a driver-supplied cleanup callback function for the object.
old-location: wdf\iwdfobject_assigncontext.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFObject::AssignContext"]
ms.keywords: AssignContext, AssignContext method, AssignContext method,IWDFObject interface, IWDFObject interface,AssignContext method, IWDFObject.AssignContext, IWDFObject::AssignContext, UMDFBaseObjectRef_1cc8c14a-66bd-487c-a58d-00f22f52adcc.xml, umdf.iwdfobject_assigncontext, wdf.iwdfobject_assigncontext, wudfddi/IWDFObject::AssignContext
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
 - IWDFObject::AssignContext
 - wudfddi/IWDFObject::AssignContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFObject::AssignContext
---

# IWDFObject::AssignContext


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AssignContext</b> method registers a context and a driver-supplied cleanup callback function for the object.

## -parameters

### -param pCleanupCallback 

[in, optional]
A pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a> interface that contains the cleanup callback function, which performs cleanup operations for the object if it becomes invalid. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification when the object is cleaned up.

### -param pContext 

[in, optional]
A pointer to the context to register. <b>NULL</b> is a valid context.

## -returns

<b>AssignContext</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## -remarks

A driver calls <b>AssignContext</b> to register a context and to request notification when the object becomes invalid. In a <b>AssignContext</b> call, the driver passes a pointer to the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a> interface in the <i>pCleanupCallback</i> parameter to register <b>IObjectCleanup</b>. Note that the framework internally holds a reference to the supplied <b>IObjectCleanup</b> interface while the object is valid. When the object becomes invalid, the framework calls the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a> method to notify the driver. The framework automatically releases the reference to the supplied <b>IObjectCleanup</b> after calling <b>IObjectCleanup::OnCleanup</b>.

At any given time, only one context that is associated with each object instance can exist. Attempts to register additional contexts fail.

A context can be associated only with an object that is in a valid state. For example, an attempt to associate a context with an object that is in the process of deletion fails.

Because the context is not a Component Object Model (COM) interface, the driver must not treat the context as such. For example, the driver cannot call the <b>AddRef</b> method on the context.

The <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-retrievecontext">IWDFObject::RetrieveContext</a> method can be used to retrieve the context that was previously registered through <b>AssignContext</b>.


#### Examples

For a code example of how to use the <b>AssignContext</b> method, see <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiotarget-formatrequestforwrite">IWDFIoTarget::FormatRequestForWrite</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iobjectcleanup">IObjectCleanup</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iobjectcleanup-oncleanup">IObjectCleanup::OnCleanup</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfobject-retrievecontext">IWDFObject::RetrieveContext</a>

