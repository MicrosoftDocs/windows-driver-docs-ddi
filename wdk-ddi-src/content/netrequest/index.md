---
UID: NA:netrequest
ms.assetid: befedaaa-2440-3e1f-b9f9-6701e6c3672b
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Netrequest.h header



This header is used by Networking drivers for Windows Vista and later. For more information, see
- [Networking drivers for Windows Vista and later](../_netvista/index.md)

Netrequest.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [NetRequestCompleteWithoutInformation function](nf-netrequest-netrequestcompletewithoutinformation.md) | Completes a NETREQUEST and supplies a completion status. |
| [NetRequestGetAdapter function](nf-netrequest-netrequestgetadapter.md) | The NetRequestGetAdapter method retrieves the NETADAPTER object associated with a NETREQUEST. This method is reserved for system use. Do not call this method from your code. |
| [NetRequestGetId function](nf-netrequest-netrequestgetid.md) | Retrieves the NDIS_OID identifier associated with the specified network request object. |
| [NetRequestGetPortNumber function](nf-netrequest-netrequestgetportnumber.md) | Retrieves the port number for the network request object. |
| [NetRequestGetSwitchId function](nf-netrequest-netrequestgetswitchid.md) | Retrieves the switch identifier for the net request. |
| [NetRequestGetType function](nf-netrequest-netrequestgettype.md) | Retrieves the request type in an OID request. |
| [NetRequestGetVPortId function](nf-netrequest-netrequestgetvportid.md) | Retrieves the VPortId for the NETREQUEST. |
| [NetRequestMethodComplete function](nf-netrequest-netrequestmethodcomplete.md) | Completes a method (OID) request. |
| [NetRequestQueryDataComplete function](nf-netrequest-netrequestquerydatacomplete.md) | Completes a query data (OID) request. |
| [NetRequestRetrieveInputOutputBuffer function](nf-netrequest-netrequestretrieveinputoutputbuffer.md) | Retrieves the input/output buffer associated with a NETREQUEST object. |
| [NetRequestSetBytesNeeded function](nf-netrequest-netrequestsetbytesneeded.md) | Sets the number of bytes needed to read or write for a control request (OID). |
| [NetRequestSetDataComplete function](nf-netrequest-netrequestsetdatacomplete.md) | Completes a set data (OID) request. |
| [NetRequestWdmGetNdisOidRequest function](nf-netrequest-netrequestwdmgetndisoidrequest.md) | Retrieves the traditional WDM NDIS_OID_REQUEST structure for the NETREQUEST. |
