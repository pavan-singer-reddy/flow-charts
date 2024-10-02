```mermaid

flowchart TD
    Start((Start)) --> HomePage[HomePage]
    
    subgraph HomePageLinks[" "]
        direction LR
        UsedEquipment[Used Equipment]
        TenderPortal[Tender Portal]
        MyWall[My Wall]
        Videos[Videos Section]
        OnlineManual[Online Manual]
        RentalMarketPlace[Rental Market Place]
        
        UsedEquipment ~~~ TenderPortal ~~~ MyWall ~~~ Videos ~~~ OnlineManual ~~~ RentalMarketPlace
    end
    
    HomePage --> HomePageLinks
    
    UsedEquipment --> ExternalWebsite[ExternalWebsite]
    ExternalWebsite --> End((End))

    TenderPortal --> DecisionTender{DecisionTender}
    DecisionTender -->|Fresh Tenders| FreshTenders[FreshTenders]
    DecisionTender -->|Tender Results| TenderResults[TenderResults]

    FreshTenders --> FilterTenders[FilterTenders]
    FilterTenders --> SearchTenders[SearchTenders]
    SearchTenders --> FilteredTenders[FilteredTenders]
    FilteredTenders --> FreshTenders

    TenderResults --> FilterResults[FilterResults]
    FilterResults --> SearchResults[SearchResults]
    SearchResults --> FilteredResults[FilteredResults]
    FilteredResults --> TenderResults

    MyWall --> DecisionWall{DecisionWall}
    DecisionWall -->|Posted by Tata Hitachi| TataHitachiPlaylist[TataHitachiPlaylist]
    DecisionWall -->|Posted by User| UserPlaylist[UserPlaylist]
    TataHitachiPlaylist & UserPlaylist --> VideosOrImages[VideosOrImages]

    Videos --> DefaultVideos[DefaultVideos]
    DefaultVideos --> SearchVideo[SearchVideo]
    SearchVideo --> FilteredVideos[FilteredVideos]

    OnlineManual --> DecisionManual{DecisionManual}
    DecisionManual -->|Mini Handbook| MiniHandbook[MiniHandbook]
    DecisionManual -->|Parts Catalogue| PartsCatalogue[PartsCatalogue]
    DecisionManual -->|Operational Manual| OperationalManual[OperationalManual]

    MiniHandbook & PartsCatalogue & OperationalManual --> Subscribe[Subscribe]
    Subscribe --> AccountPage[AccountPage]

    RentalMarketPlace --> DefaultProducts[DefaultProducts]
    DefaultProducts --> Filters[Filters]
    Filters --> FilteredProducts[FilteredProducts]

    FilteredProducts --> ViewDetails[ViewDetails]
    ViewDetails --> ProductDetails[ProductDetails]
    ProductDetails --> EnquireNow[EnquireNow]
    EnquireNow --> EnquiryPopup[EnquiryPopup]
    EnquiryPopup --> DecisionEnquiry{DecisionEnquiry}
    DecisionEnquiry -->|Submit| SuccessMessage[SuccessMessage]
    DecisionEnquiry -->|Cancel| ErrorMessage[ErrorMessage]
    ProductDetails --> GoBack[GoBack]
    GoBack --> DefaultProducts

    DefaultProducts --> DecisionViewAll{DecisionViewAll}
    DecisionViewAll -->|View All| ViewAll[ViewAll]
    ViewAll --> ShowLess[ShowLess]
    ShowLess --> DefaultView[DefaultView]
    DefaultView --> DefaultProducts

    FilteredProducts --> Interested[Interested]
    Interested --> EnquiryPopupInterested[EnquiryPopupInterested]
    EnquiryPopupInterested --> DecisionInterested{DecisionInterested}
    DecisionInterested -->|Submit| SuccessMessageInterested[SuccessMessageInterested]
    DecisionInterested -->|Cancel| ErrorMessageInterested[ErrorMessageInterested]

```