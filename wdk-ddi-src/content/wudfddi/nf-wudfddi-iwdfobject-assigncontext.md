---
UID: NF:wudfddi.IWDFObject.AssignContext
title: IWDFObject::AssignContext method
author: windows-driver-content
description: The AssignContext method registers a context and a driver-supplied cleanup callback function for the object.
old-location: wdf\iwdfobject_assigncontext.htm
old-project: wdf
ms.assetid: 9b543d5d-ed6d-4440-b5ad-aefca69dd489
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: AssignContext method, umdf.iwdfobject_assigncontext, IWDFObject interface, AssignContext method, IWDFObject, UMDFBaseObjectRef_1cc8c14a-66bd-487c-a58d-00f22f52adcc.xml, AssignContext method, IWDFObject interface, AssignContext, IWDFObject::AssignContext, wdf.iwdfobject_assigncontext, wudfddi/IWDFObject::AssignContext
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
-	IWDFObject.AssignContext
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFObject::AssignContext method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AssignContext</b> method registers a context and a driver-supplied cleanup callback function for the object.


## -syntax


````
HRESULT AssignContext(
  [in, optional] IObjectCleanup *pCleanupCallback,
  [in, optional] void           *pContext
);
````


## -parameters




### -param pCleanupCallback [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a> interface that contains the cleanup callback function, which performs cleanup operations for the object if it becomes invalid. This parameter is optional. The driver can pass <b>NULL</b> if the driver does not require notification when the object is cleaned up. 


### -param pContext [in, optional]

A pointer to the context to register. <b>NULL</b> is a valid context. 


## -returns



<b>AssignContext</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.




## -remarks



A driver calls <b>AssignContext</b> to register a context and to request notification when the object becomes invalid. In a <b>AssignContext</b> call, the driver passes a pointer to the <a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a> interface in the <i>pCleanupCallback</i> parameter to register <b>IObjectCleanup</b>. Note that the framework internally holds a reference to the supplied <b>IObjectCleanup</b> interface while the object is valid. When the object becomes invalid, the framework calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a> method to notify the driver. The framework automatically releases the reference to the supplied <b>IObjectCleanup</b> after calling <b>IObjectCleanup::OnCleanup</b>.

At any given time, only one context that is associated with each object instance can exist. Attempts to register additional contexts fail.

A context can be associated only with an object that is in a valid state. For example, an attempt to associate a context with an object that is in the process of deletion fails.

Because the context is not a Component Object Model (COM) interface, the driver must not treat the context as such. For example, the driver cannot call the <b>AddRef</b> method on the context.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560218">IWDFObject::RetrieveContext</a> method can be used to retrieve the context that was previously registered through <b>AssignContext</b>.


#### Examples

For a code example of how to use the <b>AssignContext</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560218">IWDFObject::RetrieveContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a>



<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>



<a href="..\wudfddi\nn-wudfddi-iobjectcleanup.md">IObjectCleanup</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFObject::AssignContext method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

