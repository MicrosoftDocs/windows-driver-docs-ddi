---
UID: NF:portcls.IServiceGroup.AddMember
title: IServiceGroup::AddMember method
author: windows-driver-content
description: The AddMember method adds a member to the service group.
old-location: audio\iservicegroup_addmember.htm
old-project: audio
ms.assetid: 1eddb631-db85-4243-89a4-a4ab042cee28
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: AddMember method [Audio Devices], IServiceGroup interface, IServiceGroup::AddMember, AddMember, IServiceGroup interface [Audio Devices], AddMember method, audmp-routines_0d318d56-28e9-4e42-84b3-1d0eb4110f71.xml, portcls/IServiceGroup::AddMember, AddMember method [Audio Devices], audio.iservicegroup_addmember, IServiceGroup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IServiceGroup.AddMember
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IServiceGroup::AddMember method


## -description


The <code>AddMember</code> method adds a member to the service group.


## -syntax


````
NTSTATUS AddMember(
  [in] PSERVICESINK pServiceSink
);
````


## -parameters




### -param pServiceSink [in]

Pointer to the <a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a> interface of the new member of the service group


## -returns


<code>AddMember</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.



## -remarks


The <code>AddMember</code> method calls <b>AddRef</b> on the <i>pServiceSink</i> object. When the object is later removed, the <b>RemoveMember</b> method calls <b>Release</b> on the <i>pServiceSink</i> object. This behavior is in accordance with the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.



## -see-also

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>

<a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IServiceGroup::AddMember method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

