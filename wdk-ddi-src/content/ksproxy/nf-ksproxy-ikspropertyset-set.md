---
UID: NF:ksproxy.IKsPropertySet.Set
title: IKsPropertySet::Set method
author: windows-driver-content
description: The Set method sets a property identified by a property-set GUID and a property identifier.
old-location: stream\ikspropertyset_set.htm
old-project: stream
ms.assetid: 959a78e2-b5c8-47b0-97b1-52d9565a6dab
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: Set method [Streaming Media Devices], IKsPropertySet interface [Streaming Media Devices], Set method, Set, stream.ikspropertyset_set, IKsPropertySet::Set, ksproxy/IKsPropertySet::Set, IKsPropertySet, ksproxy_957cf2a5-1dc6-4e89-86c5-b2f01d913b66.xml, Set method [Streaming Media Devices], IKsPropertySet interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h, Ksproxy.h, Dsound.h, Ksproxy.h, Ksproxy.h, Dsound.h
req.target-type: Desktop
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsPropertySet.Set
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsPropertySet::Set method


## -description


The <b>Set</b> method sets a property identified by a property-set GUID and a property identifier.


## -syntax


````
HRESULT Set(
  [in] REFGUID PropSet,
  [in] ULONG   Id,
  [in] LPVOID  InstanceData,
  [in] ULONG   InstanceLength,
  [in] LPVOID  PropertyData,
  [in] ULONG   DataLength
);
````


## -parameters




#### - PropSet [in]

GUID that identifies the property set.


#### - Id [in]

Identifier of the property within the property set. 


#### - InstanceData [in]

Pointer to instance data for the property. 


#### - InstanceLength [in]

Size, in bytes, of the buffer at <i>InstanceData</i>. 


#### - PropertyData [in]

Pointer to a buffer that contains the value of the property to set. 


#### - DataLength [in]

Size, in bytes, of the buffer at <i>PropertyData</i>. 


## -returns


Returns NOERROR if successful; otherwise, returns an error code.



## -remarks


<div class="alert"><b>Warning</b>  <p class="note">Header files <i>ksproxy.h</i> and <i>dsound.h</i> define similar but incompatible versions of the <b>IKsPropertySet</b> interface. Applications that require the KS proxy module should use the version defined in <i>ksproxy.h</i>. The DirectSound version of <b>IKsPropertySet</b> is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.

<p class="note">

If an application must include both <i>ksproxy.h</i> and <i>dsound.h</i>, whichever header file the compiler scans first is the one whose definition of <b>IKsPropertySet</b> is used by the compiler.



</div><div> </div>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560719">IKsPropertySet::Get</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPropertySet::Set method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

