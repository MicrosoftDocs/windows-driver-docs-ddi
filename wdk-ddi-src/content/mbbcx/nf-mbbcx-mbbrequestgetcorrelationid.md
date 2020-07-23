---
UID: NF:mbbcx.MbbRequestGetCorrelationId
title: MbbRequestGetCorrelationId function (mbbcx.h)
description: Client drivers can call the MbbRequestGetCorrelationId method to correlate a pair of send and receive requests that exchange MBIM control messages between the MBBCx framework and the client driver.
tech.root: netvista
ms.assetid: 666340d8-3c73-4072-afbb-a51267d307ac
ms.date: 06/29/2018
keywords: ["MbbRequestGetCorrelationId function"]
f1_keywords:
 - "mbbcx/MbbRequestGetCorrelationId"
 - "MbbRequestGetCorrelationId"
ms.keywords: MbbRequestGetCorrelationId
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: mbbcxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- mbbcxstub.lib
api_name: 
- MbbRequestGetCorrelationId
targetos: Windows


ms.custom: RS5
---

# MbbRequestGetCorrelationId function


## -description



Client drivers can call the **MbbRequestGetCorrelationId** method to correlate a pair of send and receive requests that exchange MBIM control messages between the MBBCx framework and the client driver.

## -parameters

### -param Request

A handle to the framework object that represents a request from the MBBCx framework, either to send a MBIM control command message to the device or to receive an MBIM control response message from the device.

## -returns

Returns a GUID value.

The GUID's purpose is similar to the **TransactionId** field of the MBIM message header defined in the MBIM specification. The MBBCx framework provides this value, so the client driver is not required to parse the MBIM message if some sort of correlation is needed. 

## -remarks

The MBBCx framework calls into the client driver to issue an MBIM command message, and later calls into the client driver again to retreive the response message for that command. The GUID value returned for both calls will be the same, and it would only change if a new command and response message pair is requested.

Sometimes, the command and response message pair might get fragemented due to size limitations. In that case, all fragments from the same pair will have the same GUID value.

## -see-also
