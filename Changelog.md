﻿# Changelog
This page defines all the changes that were done in the API. There is a difference between the version of the API and the version of iProva. A new major API version will only be created when we have to introduce breaking changes to the API. New routes, enhanced routes and bug fixes can be introduced with a new iProva version without creating a new API version.

## Changes in iProva 5.6.1.0

Change|Route|Remarks
|--|--|--|
Fixed|-|Users having two factor authentication enabled now also have to pass a security code to the api when authenticating. For more info, see the general usage information of the API
Added|-|From this version on, the preferred way of authenticating is using bearer tokens. For more info, see the general usage information of the API
Added|**POST** `api/bearer_tokens` |Added this route to be able to generate a bearer token for the new bearer authentication

## Changes in iProva 5.6.0.3

Change|Route|Remarks
|--|--|--|
Changed|**GET** `api/versions/iprova` |The version now includes the minor version. Example: old: 5.6.0 , new: 5.6.0.3
Added|**GET/PUT** `api/apps/settings` |Added this route to be able to get and set settings for apps
Added|**POST** `api/apps/{app_name}/feedback` |Added this route to be able to post feedback on an app to iProva

## Changes in iProva 5.6.0

Change|Route|Remarks
|--|--|--|
Changed|**ANY** `api/card_files/{card_file_id}/cards` and `api/card_files/cards/{card_id}` |Added nfc_code, qr_code, bluetooth_low_energy_beacon, gps_location_longitude and gps_location_latitude attributes to the first level of cards
Added|**GET** `api/card_files/cards/{card_id}/documents` |Added this route to retrieve all published documents linked to the card
Added|**GET** `api/documents/{document_id}` and the `contents` and `download` sub routes|Get meta data, contents and binary data from the published version of a document
Added|**GET** `api/documents/bulk_exports`|Get meta data and the output of bulk exports of documents
Added|**GET** `api/documents/document_media/{document_media_item_id}/download`|Download a media item (audio, video) from a document. The media item is found in documents using a <mediaitem> tag. The attribute "data-document-media-item-id" contains the "document_media_item_id" parameter you need to pass to this method
Added|**GET** `api/hyperlinks/{hyperlink_id}`|Gets information of the target of a hyperlink. The {hyperlink_id} can be found by reading the data-hyperlinkid attribute of an anchor tag in an html document
Added|**GET** `api/portals/themes`|Gets the list of portal themes for the current user.
Fixed|**GET** `api/card_files/cards` and sub routes|last_modified_datetime of cards were never filled
Fixed|**GET** routes returning a date|Made it clear an UTC date is returned

## Changes in iProva 5.5.0

Change|Route|Remarks
|--|--|--|
Added|**POST** `api/tokens`|Create tokens to login into the API
Added|**GET** `api/versions`|Get the current API and iProva versions
Added|**ANY** `api/card_files` and all sub routes|Retrieve card files and manage cards

**ANY** is all in iProva supported verbs.


## API versions in iProva version

|API version|iProva version|Remarks
|--|--|--|
|1.0|5.5.0 - present|REST API introduced for tokens, versions and card files|
