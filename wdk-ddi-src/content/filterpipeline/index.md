---
UID: NA:filterpipeline
ms.assetid: 434b4bef-ac82-3eee-8cc8-8fbfd4bad71c
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Filterpipeline.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Filterpipeline.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [DrvPopulateFilterServices function](nf-filterpipeline-drvpopulatefilterservices.md) | The DrvPopulateFilterServices function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate filter service objects in the filter pipeline property bag specified by the pPropertyBag parameter. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0001 enumeration](ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0001.md) | The ExpsCompressionOptions enumeration describes compression options for an XPS part. |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0002 enumeration](ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0002.md) | The EXpsFontOptions enumeration describes the font options for an XPS part. |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0003 enumeration](ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0003.md) | The EXpsJobConsumption enumeration describes job consumption updates. |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0004 enumeration](ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0004.md) | "." |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IFixedDocument interface](nn-filterpipeline-ifixeddocument.md) | The IFixedDocument interface represents a fixed document for an XPS document sequence. |
| [IFixedDocumentSequence interface](nn-filterpipeline-ifixeddocumentsequence.md) | The IFixedDocumentSequence interface represents the fixed document sequence for an XPS document. |
| [IFixedPage interface](nn-filterpipeline-ifixedpage.md) | A filter uses the IFixedPage interface to work with fixed pages in an XPS document. |
| [IInterFilterCommunicator interface](nn-filterpipeline-iinterfiltercommunicator.md) | The IInterFilterCommunicator interface is implemented in an object that resides in the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface. |
| [IPartBase interface](nn-filterpipeline-ipartbase.md) | The IPartBase interface is a common base for document part interfaces. |
| [IPartColorProfile interface](nn-filterpipeline-ipartcolorprofile.md) | The IPartColorProfile interface is the abstraction for an XPS color profile. |
| [IPartDiscardControl interface](nn-filterpipeline-ipartdiscardcontrol.md) | The filter pipeline supports the discard control. |
| [IPartFont interface](nn-filterpipeline-ipartfont.md) | The IPartFont interface is the abstraction for fonts in a part. |
| [IPartFont2 interface](nn-filterpipeline-ipartfont2.md) | "." |
| [IPartImage interface](nn-filterpipeline-ipartimage.md) | The IPartImage interface is the abstraction for images in an XPS document. |
| [IPartPrintTicket interface](nn-filterpipeline-ipartprintticket.md) | The IPartPrintTicket interface is the abstraction for a print ticket in an XPS document. |
| [IPartResourceDictionary interface](nn-filterpipeline-ipartresourcedictionary.md) | The IPartResourceDictionary interface is the abstraction for an XPS resource dictionary. |
| [IPartThumbnail interface](nn-filterpipeline-ipartthumbnail.md) | The IPartThumbnail interface is an abstraction for thumbnails in an XPS document. |
| [IPrintClassObjectFactory interface](nn-filterpipeline-iprintclassobjectfactory.md) | TheIPrintClassObjectFactory interface creates print filter-related interfaces. |
| [IPrintPipelineFilter interface](nn-filterpipeline-iprintpipelinefilter.md) | The methods in the IPrintPipelineFilter interface are called for initialization and shutdown. A filter must implement these methods. |
| [IPrintPipelineManagerControl interface](nn-filterpipeline-iprintpipelinemanagercontrol.md) | The IPrintPipelineManagerControl interface is passed to each filter in the IPrintPipelineFilter |
| [IPrintPipelineProgressReport interface](nn-filterpipeline-iprintpipelineprogressreport.md) | A rendering filter uses the IPrintPipelineProgressReport interface to send progress status to a spooler. |
| [IPrintPipelinePropertyBag interface](nn-filterpipeline-iprintpipelinepropertybag.md) | The IPrintPipelinePropertyBag interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface. IprintPipelinePropertyBag inherits from the IUnknown interface. |
| [IPrintReadStream interface](nn-filterpipeline-iprintreadstream.md) | Filters use the IPrintReadStream interface to read data as a raw stream of bytes. |
| [IPrintReadStreamFactory interface](nn-filterpipeline-iprintreadstreamfactory.md) | The IPrintReadStreamFactory interface creates a stream reader that a filter can use to access the stream. For example, a filter could use this stream to access the per-user print ticket. |
| [IPrintWriteStream interface](nn-filterpipeline-iprintwritestream.md) | Filters use the IPrintWriteStream interface to write data as a raw stream of bytes. |
| [IPrintWriteStreamFlush interface](nn-filterpipeline-iprintwritestreamflush.md) | Filters use the IPrintWriteStreamFlush interface to explicitly flush data as a raw stream of bytes from a filter. This interface is retrieved through IPrintWriteStream |
| [IXpsDocument interface](nn-filterpipeline-ixpsdocument.md) | The IXpsDocument interface represents the root of an XPS document. |
| [IXpsDocumentConsumer interface](nn-filterpipeline-ixpsdocumentconsumer.md) | A filter uses the IXpsDocumentConsumer interface when it generates XPS content for the pipeline to consume. |
| [IXpsDocumentProvider interface](nn-filterpipeline-ixpsdocumentprovider.md) | The IxpsDocumentProvider interface provides interfaces to consume parts of a document. |
| [IXpsPartIterator interface](nn-filterpipeline-ixpspartiterator.md) | The IXpsPartIterator interface is an iterator for XPS parts. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IFixedDocument::GetPrintTicket method](nf-filterpipeline-ifixeddocument-getprintticket.md) | The GetPrintTicket method gets the print ticket object for the fixed document. |
| [IFixedDocument::GetUri method](nf-filterpipeline-ifixeddocument-geturi.md) | The GetUri method gets the URI of the fixed document. |
| [IFixedDocument::SetPrintTicket method](nf-filterpipeline-ifixeddocument-setprintticket.md) | The SetPrintTicket method inserts a print ticket into the fixed document. |
| [IFixedDocumentSequence::GetPrintTicket method](nf-filterpipeline-ifixeddocumentsequence-getprintticket.md) | The GetPrintTicket method gets the print ticket object for the fixed document sequence. |
| [IFixedDocumentSequence::GetUri method](nf-filterpipeline-ifixeddocumentsequence-geturi.md) | The GetUri method gets the URI of the fixed document sequence. |
| [IFixedDocumentSequence::SetPrintTicket method](nf-filterpipeline-ifixeddocumentsequence-setprintticket.md) | The SetPrintTicket method inserts a print ticket into the fixed document sequence. |
| [IFixedPage::DeleteResource method](nf-filterpipeline-ifixedpage-deleteresource.md) | The DeleteResource method deletes a resource that is associated with the page. |
| [IFixedPage::GetPagePart method](nf-filterpipeline-ifixedpage-getpagepart.md) | The GetPagePart method gets the images, thumbnails, fonts, and so on in a page by using the URI. |
| [IFixedPage::GetPrintTicket method](nf-filterpipeline-ifixedpage-getprintticket.md) | The GetPrintTicket method gets the print ticket object for the fixed page. |
| [IFixedPage::GetWriteStream method](nf-filterpipeline-ifixedpage-getwritestream.md) | The GetWriteStream method retrieves the stream object to write page markup to read . You can use this stream to change page markup. |
| [IFixedPage::GetXpsPartIterator method](nf-filterpipeline-ifixedpage-getxpspartiterator.md) | The GetXpsPartIterator method gets an iterator to enumerate all of the parts that are associated with the page. |
| [IFixedPage::SetPagePart method](nf-filterpipeline-ifixedpage-setpagepart.md) | The SetPagePart method associates a new part with the page. |
| [IFixedPage::SetPrintTicket method](nf-filterpipeline-ifixedpage-setprintticket.md) | The SetPrintTicket method associates a print ticket with the page. |
| [IInterFilterCommunicator::RequestReader method](nf-filterpipeline-iinterfiltercommunicator-requestreader.md) | The RequestReader method retrieves the reader interface for an IInterFilterCommunicator object. |
| [IInterFilterCommunicator::RequestWriter method](nf-filterpipeline-iinterfiltercommunicator-requestwriter.md) | The RequestWriter method retrieves the writer interface for an IInterFilterCommunicator object. |
| [IPartBase::GetPartCompression method](nf-filterpipeline-ipartbase-getpartcompression.md) | The GetPartCompression method gets the compression of the part. |
| [IPartBase::GetStream method](nf-filterpipeline-ipartbase-getstream.md) | The GetStream method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup). |
| [IPartBase::GetUri method](nf-filterpipeline-ipartbase-geturi.md) | The GetUri method gets the URI of the part. |
| [IPartBase::SetPartCompression method](nf-filterpipeline-ipartbase-setpartcompression.md) | The SetPartCompression method sets the compression of the part. |
| [IPartDiscardControl::GetDiscardProperties method](nf-filterpipeline-ipartdiscardcontrol-getdiscardproperties.md) | The GetDiscardProperties method gets the properties of the discard control. |
| [IPartFont2::GetFontRestriction method](nf-filterpipeline-ipartfont2-getfontrestriction.md) | "." |
| [IPartFont::GetFontProperties method](nf-filterpipeline-ipartfont-getfontproperties.md) | The GetFontProperties method gets the font properties. |
| [IPartFont::SetFontContent method](nf-filterpipeline-ipartfont-setfontcontent.md) | The SetFontContent method sets the content of the font. |
| [IPartFont::SetFontOptions method](nf-filterpipeline-ipartfont-setfontoptions.md) | The SetFontOptions method sets the options for the font. |
| [IPartImage::GetImageProperties method](nf-filterpipeline-ipartimage-getimageproperties.md) | The GetImageProperties method gets an image property that is based on the content type. |
| [IPartImage::SetImageContent method](nf-filterpipeline-ipartimage-setimagecontent.md) | The SetImageContent method sets an image property that is based on the content type. |
| [IPartThumbnail::GetThumbnailProperties method](nf-filterpipeline-ipartthumbnail-getthumbnailproperties.md) | The GetThumbnailProperties method gets the thumbnail properties. |
| [IPartThumbnail::SetThumbnailContent method](nf-filterpipeline-ipartthumbnail-setthumbnailcontent.md) | The SetThumbnailContent method sets the thumbnail content for the part. |
| [IPrintClassObjectFactory::GetPrintClassObject method](nf-filterpipeline-iprintclassobjectfactory-getprintclassobject.md) | The GetPrintClassObject method creates a print filter-related object for a specified printer by using the IID of the interface object to create. |
| [IPrintPipelineFilter::InitializeFilter method](nf-filterpipeline-iprintpipelinefilter-initializefilter.md) | The InitializeFilter method initializes a filter. |
| [IPrintPipelineFilter::ShutdownOperation method](nf-filterpipeline-iprintpipelinefilter-shutdownoperation.md) | The Pipeline Manager uses the ShutdownOperation method to shut down a filter if the print job is canceled or an error occurs. |
| [IPrintPipelineFilter::StartOperation method](nf-filterpipeline-iprintpipelinefilter-startoperation.md) | The StartOperation method starts the operation of a filter. The filter reads, processes, and writes data in this method. |
| [IPrintPipelineManagerControl::FilterFinished method](nf-filterpipeline-iprintpipelinemanagercontrol-filterfinished.md) | The FilterFinished method reports that a filter is finished processing. |
| [IPrintPipelineManagerControl::RequestShutdown method](nf-filterpipeline-iprintpipelinemanagercontrol-requestshutdown.md) | The RequestShutdown method requests that a pipeline be shut down. |
| [IPrintPipelineProgressReport::ReportProgress method](nf-filterpipeline-iprintpipelineprogressreport-reportprogress.md) | The ReportProgress method reports the progress of the XPS job consumption to the pipeline manager. |
| [IPrintPipelinePropertyBag::AddProperty method](nf-filterpipeline-iprintpipelinepropertybag-addproperty.md) | The AddProperty method adds a property to a property bag. |
| [IPrintPipelinePropertyBag::DeleteProperty method](nf-filterpipeline-iprintpipelinepropertybag-deleteproperty.md) | The DeleteProperty method deletes a property from a property bag. |
| [IPrintPipelinePropertyBag::GetProperty method](nf-filterpipeline-iprintpipelinepropertybag-getproperty.md) | The GetProperty method gets a property from a property bag. |
| [IPrintReadStream::ReadBytes method](nf-filterpipeline-iprintreadstream-readbytes.md) | The ReadBytes method reads a number of bytes into a buffer. |
| [IPrintReadStream::Seek method](nf-filterpipeline-iprintreadstream-seek.md) | The Seek method changes the seek pointer to a new location in the stream. |
| [IPrintReadStreamFactory::GetStream method](nf-filterpipeline-iprintreadstreamfactory-getstream.md) | The GetStream method gets the stream interface. |
| [IPrintWriteStream::Close method](nf-filterpipeline-iprintwritestream-close.md) | The Close method closes a stream and ends the writing to that stream. This method is mandatory. You must call this method when the filter is done writing. |
| [IPrintWriteStream::WriteBytes method](nf-filterpipeline-iprintwritestream-writebytes.md) | The WriteBytes method writes a specified number of bytes to a stream. |
| [IPrintWriteStreamFlush::FlushData method](nf-filterpipeline-iprintwritestreamflush-flushdata.md) | The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream. |
| [IXpsDocument::GetThumbnail method](nf-filterpipeline-ixpsdocument-getthumbnail.md) | The GetThumbnail method gets the document thumbnail object. |
| [IXpsDocument::SetThumbnail method](nf-filterpipeline-ixpsdocument-setthumbnail.md) | The SetThumbnail method removes the current thumbnail object from the document and inserts a new one. |
| [IXpsDocumentConsumer::CloseSender method](nf-filterpipeline-ixpsdocumentconsumer-closesender.md) | The CloseSender method tells the Pipeline Manager that the filter is done sending XPS parts. |
| [IXpsDocumentConsumer::GetNewEmptyPart method](nf-filterpipeline-ixpsdocumentconsumer-getnewemptypart.md) | The GetNewEmptyPart method creates a new XPS part. |
| [IXpsDocumentConsumer::SendFixedDocument method](nf-filterpipeline-ixpsdocumentconsumer-sendfixeddocument.md) | The SendFixedDocument method sends a fixed document object to the pipeline. |
| [IXpsDocumentConsumer::SendFixedDocumentSequence method](nf-filterpipeline-ixpsdocumentconsumer-sendfixeddocumentsequence.md) | The SendFixedDocumentSequence method sends a fixed document sequence to the pipeline. |
| [IXpsDocumentConsumer::SendFixedPage method](nf-filterpipeline-ixpsdocumentconsumer-sendfixedpage.md) | The SendFixedPage method sends a fixed page of an XPS document to the pipeline. |
| [IXpsDocumentConsumer::SendXpsDocument method](nf-filterpipeline-ixpsdocumentconsumer-sendxpsdocument.md) | The SendXpsDocument method sends an XPS document to the pipeline. |
| [IXpsDocumentConsumer::SendXpsUnknown method](nf-filterpipeline-ixpsdocumentconsumer-sendxpsunknown.md) | The SendXpsUnknown method sends an XPS document part that cannot be identified to the filter pipeline. |
| [IXpsDocumentProvider::GetXpsPart method](nf-filterpipeline-ixpsdocumentprovider-getxpspart.md) | The GetXpsPart method retrieves several objects that make up an XPS document. |
| [IXpsPartIterator::Current method](nf-filterpipeline-ixpspartiterator-current.md) | The Current method provides the current URI and part. |
| [IXpsPartIterator::IsDone method](nf-filterpipeline-ixpspartiterator-isdone.md) | The IsDone method determines whether the iterator has finished the iteration. |
| [IXpsPartIterator::Next method](nf-filterpipeline-ixpspartiterator-next.md) | The Next method advances the iterator to the next part. |
| [IXpsPartIterator::Reset method](nf-filterpipeline-ixpspartiterator-reset.md) | The Reset method sets the iterator to the first element. |
