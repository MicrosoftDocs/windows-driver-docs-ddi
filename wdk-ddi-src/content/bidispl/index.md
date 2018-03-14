---
UID: NA:bidispl
ms.assetid: 646004d0-de46-3d2d-a566-a0e536a5a832
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Bidispl.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Bidispl.h contain these programming interfaces:


## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IBidiRequest interface](nn-bidispl-ibidirequest.md) | The IBidiRequest interface allows an application or other objects to compose a bidi request. |
| [IBidiRequestContainer interface](nn-bidispl-ibidirequestcontainer.md) | The IBidiRequestContainer interface allows an application or other objects to compose and retrieve a list of bidi requests. |
| [IBidiSpl interface](nn-bidispl-ibidispl.md) | The IBidiSpl interface allows an application or other objects to send a single bidi request or a list of bidi requests. |
| [IBidiSpl2 interface](nn-bidispl-ibidispl2.md) | The IBidiSpl2 interface enables an application or other objects to send one or more bidi requests using one of the Bidi Request Schemas and receive information formatted as one of the Bidi Response Schemas. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IBidiRequest::GetEnumCount method](nf-bidispl-ibidirequest-getenumcount.md) | The GetEnumCount method gets the number of output results from the bidi request. |
| [IBidiRequest::GetOutputData method](nf-bidispl-ibidirequest-getoutputdata.md) | The GetOutputData method gets the specified output data coming back from the printer. |
| [IBidiRequest::GetResult method](nf-bidispl-ibidirequest-getresult.md) | The GetResult method tells whether the bidi request was successful. |
| [IBidiRequest::SetInputData method](nf-bidispl-ibidirequest-setinputdata.md) | The SetInputData method sets the data to send to the printer. |
| [IBidiRequest::SetSchema method](nf-bidispl-ibidirequest-setschema.md) | The SetSchema method sets the bidi schema string. |
| [IBidiRequestContainer::AddRequest method](nf-bidispl-ibidirequestcontainer-addrequest.md) | The AddRequest method adds a request to the request list. |
| [IBidiRequestContainer::GetEnumObject method](nf-bidispl-ibidirequestcontainer-getenumobject.md) | The GetEnumObject method enumerates the bidi requests in a list. |
| [IBidiRequestContainer::GetRequestCount method](nf-bidispl-ibidirequestcontainer-getrequestcount.md) | The GetRequestCount method gets the number of requests in the request list. |
| [IBidiSpl2::BindDevice method](nf-bidispl-ibidispl2-binddevice.md) | The BindDevice method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the OpenPrinter function. |
| [IBidiSpl2::SendRecvXMLStream method](nf-bidispl-ibidispl2-sendrecvxmlstream.md) | The SendRecvXMLStream method sends a bidirectional printer communication request and receives the response as IStream objects formatted in accordance with the Bidirectional Communication Schemas. |
| [IBidiSpl2::SendRecvXMLString method](nf-bidispl-ibidispl2-sendrecvxmlstring.md) | The SendRecvXMLString method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the Bidirectional Communication Schemas. |
| [IBidiSpl2::UnbindDevice method](nf-bidispl-ibidispl2-unbinddevice.md) | The UnbindDevice method releases a printer from a bidirectional printer communication (bidi communication) request. |
| [IBidiSpl::BindDevice method](nf-bidispl-ibidispl-binddevice.md) | The BindDevice method binds a printer to a bidi request. This method is similar to the OpenPrinter function. |
| [IBidiSpl::MultiSendRecv method](nf-bidispl-ibidispl-multisendrecv.md) | The MultiSendRecv method sends a list of bidi requests. |
| [IBidiSpl::SendRecv method](nf-bidispl-ibidispl-sendrecv.md) | The SendRecv method sends a bidi request to the printer. |
| [IBidiSpl::UnbindDevice method](nf-bidispl-ibidispl-unbinddevice.md) | The UnbindDevice method unbinds a printer from a bidi request. |
