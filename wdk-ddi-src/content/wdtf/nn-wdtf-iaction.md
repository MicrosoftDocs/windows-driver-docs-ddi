---
UID: NN:wdtf.IAction
title: IAction
author: windows-driver-content
description: The IAction interfaces are plug-ins that can control an instance of the IWDTFTarget2 interface.
old-location: dtf\iaction.htm
old-project: dtf
ms.assetid: 9bc709cb-1adb-4b70-b8cb-9168ccb7b259
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dtf.iaction, IAction interface [Windows Device Testing Framework], IAction interface [Windows Device Testing Framework], described, IAction, wdtf/IAction, Microsoft.WDTF.IAction, IAction_d82d1b27-acd4-43f6-b020-a9a9fa5dbe60.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IAction
-	IAction.SetTarget
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IAction interface


## -description


The <b>IAction</b> interfaces are plug-ins that can control an instance of the 
<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a> interface.


## -members

The <b>IAction</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%"><b>SetTarget</b></td>
<td align="left" width="63%">
You should not directly call this method. <b>SetTarget</b> is used internally by 
the <a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a> method to find the correct implementation as well as provide the targets for the implementation to use in whatever actions it performs.

</td>
</tr>
</table>You should not directly call this method. <b>SetTarget</b> is used internally by 
the <a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a> method to find the correct implementation as well as provide the targets for the implementation to use in whatever actions it performs.

 


## -remarks



You can retrieve an <b>IAction</b> interface for a target by calling 
<a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a>.

The <b>IAction</b> interface inherits from <a href="..\wdtf\nn-wdtf-itracing.md">ITracing</a>. You can use <b>ITracing</b> to set the trace level of the action.

Domain experts use this interface as a base for implementing a WDTF plug-in (that is, action) that can 
control an instance of an <a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a> interface. For more information about action interfaces, see <a href="https://msdn.microsoft.com/b329e9a2-7d24-4612-9aa1-9d7955a61473">Controlling Targets</a>.

For a listing of all action interfaces included in WDTF, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538355">Action Interfaces</a>.




## -see-also

<a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a>



<a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a>



<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IAction interface%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

