---
UID: NF:ks.KsValidateConnectRequest
title: KsValidateConnectRequest function
author: windows-driver-content
description: The KsValidateConnectRequest function validates a connection request and returns a pointer to the connection structure associated with the request.This function can only be called at PASSIVE_LEVEL.
old-location: stream\ksvalidateconnectrequest.htm
old-project: stream
ms.assetid: 64343a8a-9629-469e-95a3-b9c140cdd324
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ksfunc_2df36f34-31c9-48f2-859c-1829b60fbae7.xml, KsValidateConnectRequest, KsValidateConnectRequest function [Streaming Media Devices], ks/KsValidateConnectRequest, stream.ksvalidateconnectrequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsValidateConnectRequest
product: Windows
targetos: Windows
req.typenames: 
---

# KsValidateConnectRequest function


## -description


The <b>KsValidateConnectRequest</b> function validates a connection request and returns a pointer to the connection structure associated with the request.

This function can only be called at PASSIVE_LEVEL.


## -syntax


````
NTSTATUS KsValidateConnectRequest(
  _In_        PIRP             Irp ,
  _In_        ULONG            DescriptorsCount ,
  _In_  const KSPIN_DESCRIPTOR *Descriptor ,
  _Out_       PKSPIN_CONNECT   *Connect 
);
````


## -parameters




### -param Irp [in]

Pointer to an IRP specifying the connection request.


### -param DescriptorsCount [in]

Specifies the number of pin descriptors passed.


### -param Descriptor [in]

Specifies a pointer to the list of <a href="..\ks\ns-ks-kspin_descriptor.md">KSPIN_DESCRIPTOR</a> structures.


### -param Connect [out]

Specifies a location in which to place a pointer to the <a href="..\ks\ns-ks-kspin_connect.md">KSPIN_CONNECT</a> pointer passed to the create request. If <b>KsValidateConnectRequest</b>  returns success, then Connect+1 will contain a pointer to the KSDATAFORMAT with which the pin was opened.


## -returns



The <b>KsValidateConnectRequest</b> function returns STATUS_SUCCESS if successful, or it returns an error.




## -remarks



The <b>KsValidateConnectRequest</b> function handles basic connection structure access exceptions and validates the communication requirements, medium, protocol, and basic data format. The validation performed on the data format passed is based on the data range list for the specified pin against which a pin instance is to be created. Validation is successful in three instances: if a range major format is a wildcard, the range major format matches and the range subformat is a wildcard, or the range major format, range subformat, and the range specifier all match.

The buffer is passed a copy of the original input buffer, if the originator was not in kernel mode, and is therefore safe to access.



