---
UID: NC:ndkpi.NDK_FN_CREATE_LISTENER
title: NDK_FN_CREATE_LISTENER
author: windows-driver-content
description: The NdkCreateListener (NDK_FN_CREATE_LISTENER) function creates an NDK listener object.
old-location: netvista\ndk_fn_create_listener.htm
old-project: netvista
ms.assetid: CC6259B8-AF3B-4FCE-94E3-7A5CD80C64A7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkCreateListener
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_CREATE_LISTENER callback



## -description
The <i>NdkCreateListener</i> (<i>NDK_FN_CREATE_LISTENER</i>) function creates an NDK listener object.



## -prototype

````
NDK_FN_CREATE_LISTENER NdkCreateListener;

NTSTATUS NdkCreateListener(
  _In_     NDK_ADAPTER                   *pNdkAdapter,
  _In_     NDK_FN_CONNECT_EVENT_CALLBACK ConnectEvent,
  _In_opt_ PVOID                         ConnectEventContext,
  _In_     NDK_FN_CREATE_COMPLETION      CreateCompletion,
  _In_opt_ PVOID                         RequestContext,
           _Outptr_ NDK_LISTENER         **ppNdkListener
)
{ ... }
````


## -parameters

### -param pNdkAdapter [in]

A pointer to an NDK adapter object (<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>).


### -param ConnectEvent [in]

A pointer to the <i>NdkConnectEventCallback </i> function   (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>) that the provider uses to notify the consumer for each incoming connection request.


### -param ConnectEventContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkConnectEventCallback </i> function that is specified in the <i>ConnectEvent</i> parameter.


### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.


### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.


### -param ppNdkListener 

A pointer to the created NDK  listener object (<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>) is returned in this location if request succeeds without returning STATUS_PENDING. If <i>NdkCreateListener</i> returns STATUS_PENDING this parameter is ignored and the created object is returned  with the callback that is specified in the  <i>CreateCompletion</i> parameter.


## -returns
The <i>NdkCreateListener</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The listener object was created successfully and returned with the <i>*ppNdkListener</i> parameter.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter(<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The request failed due to insufficient resources. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 


## -remarks
The <i>NdkCreateListener</i> function creates an NDK listener object. If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkListener</i> parameter. If <i>NdkCreateListener</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.


## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_adapter.md">NDK_ADAPTER</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_adapter_dispatch.md">NDK_ADAPTER_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_LISTENER callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

