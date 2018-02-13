---
UID: NF:rxce.RxCeBuildConnectionOverMultipleTransports
title: RxCeBuildConnectionOverMultipleTransports function
author: windows-driver-content
description: RxCeBuildConnectionOverMultipleTransports establishes a connection between a local RDBSS connection address and a given remote address and supports multiple transports.
old-location: ifsk\rxcebuildconnectionovermultipletransports.htm
old-project: ifsk
ms.assetid: 9ef9a5a5-e0ad-46c0-8193-8d2a18a21ea0
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: rxce/RxCeBuildConnectionOverMultipleTransports, RxCeBuildConnectionOverMultipleTransports routine [Installable File System Drivers], ifsk.rxcebuildconnectionovermultipletransports, RxCeBuildConnectionOverMultipleTransports, rxref_813ee01b-f378-4598-813a-4f2f3c47189f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxce.h
apiname:
-	RxCeBuildConnectionOverMultipleTransports
product: Windows
targetos: Windows
req.typenames: "*LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS"
req.product: Windows 10 or later.
---

# RxCeBuildConnectionOverMultipleTransports function


## -description


<b>RxCeBuildConnectionOverMultipleTransports</b> establishes a connection between a local RDBSS connection address and a given remote address and supports multiple transports. A set of local addresses are specified and this routine attempts to connect to the target server via all the transports associated with the local addresses. One connection is chosen as the winner depending on the connect options.


## -syntax


````
NTSTATUS RxCeBuildConnectionOverMultipleTransports(
  _Inout_ PRDBSS_DEVICE_OBJECT                pMiniRedirectorDeviceObject,
  _In_    RXCE_CONNECTION_CREATE_OPTIONS      CreateOptions,
  _In_    ULONG                               NumberOfAddresses,
  _In_    PRXCE_ADDRESS                       *pLocalAddressPointers,
  _In_    PUNICODE_STRING                     pServerName,
  _In_    PRXCE_CONNECTION_INFORMATION        pConnectionInformation,
  _In_    PRXCE_CONNECTION_EVENT_HANDLER      pHandler,
  _In_    PVOID                               pEventContext,
  _In_    PRXCE_CONNECTION_COMPLETION_ROUTINE pCompletionRoutine,
  _Inout_ PRXCE_CONNECTION_COMPLETION_CONTEXT pCompletionContext
);
````


## -parameters




### -param pMiniRedirectorDeviceObject [in, out]

A pointer to the mini-redirector device object.


### -param CreateOption

TBD


### -param NumberOfAddresses [in]

The number of local addresses (transports).


### -param pLocalAddressPointers [in]

A pointer to an array of the local address handles.


### -param pServerName [in]

A pointer to the name of the server (for connection enumeration).


### -param pConnectionInformation [in]

A pointer to the connection information that specifies the remote address.


### -param pHandler [in]

A pointer to the event handler for processing receive indications.


### -param pEventContext [in]

A pointer to the context parameter to be passed back to the event handler and used for indications.


### -param pCompletionRoutine [in]

A pointer to a connection completion routine when this routine completed if STATUS_PENDING is initially returned.


### -param pCompletionContext [in, out]

On input, this parameter contains a pointer to an uninitialized RXCE_CONNECTION_COMPLETION_CONTEXT structure. On output when this call is successful, the virtual circuit is associated with the connection and the virtual circuit and connection are properly initialized.


#### - CreateOptions [in]

Create options that determine which transport will be selected for establishing a connection. These options can be one of the following enumerations for RXCE_CONNECTION_CREATE_OPTIONS:





#### RxCeSelectFirstSuccessfulTransport

Select the first successful transport that responds.



#### RxCeSelectBestSuccessfulTransport

Select the best successful transport that responds.



#### RxCeSelectAllSuccessfulTransports

Select all of the successful transports that respond.


## -returns



<b>RxCeBuildConnectionOverMultipleTransports</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
It was not possible to initialize a connection and a virtual circuit with any of the multiple transports. This error can occur if all of the RDBSS transports or the RBDSS connection engine addresses pointed to in the <i>pLocalAddressPointers</i> array are invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters passed to this routine was invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
One of the asynchronous calls to the different transports passed as input parameters to the routine is still outstanding and has not been completed. 

</td>
</tr>
</table>
 




## -remarks



<b>RxCeBuildConnectionOverMultipleTransports</b> will initiate a series of asynchronous calls to all of the different transports passed in as parameters to try and build a connection. The network mini-redirector cannot be unloaded until all of these asynchronous requests are completed.

<b>RxCeBuildConnectionOverMultipleTransports</b> must be called in the context of a system worker thread.

When <b>RxCeBuildConnectionOverMultipleTransports</b> is successful, the virtual circuit will be properly initialized and connections will be established.

<b>RXCE_CONNECTION_INFORMATION</b> is a typedef for a <b>TDI_CONNECTION_INFORMATION</b> structure. 




## -see-also

<a href="..\rxce\nf-rxce-rxcebuildconnection.md">RxCeBuildConnection</a>



<a href="..\rxce\nf-rxce-rxceteardownconnection.md">RxCeTearDownConnection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565085">TDI_CONNECTION_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeBuildConnectionOverMultipleTransports routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

