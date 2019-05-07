# ![LOGO](logo.png) Freesound **flow**ground Connector

## Description

A generated **flow**ground connector for the Freesound API (version 2.0.0).

Generated from: https://api.apis.guru/v2/specs/freesound.org/2.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:40:47+03:00

## API Description

With the Freesound APIv2 you can browse, search, and retrieve information about Freesound users, packs, and the sounds themselves of course. You can find similar sounds to a given target (based on content analysis) and retrieve automatically extracted features from audio files, as well as perform advanced queries combining content analysis features and other metadata (tags, etc...). With the Freesound APIv2, you can also upload, comment, rate and bookmark sounds!

## Authorization

This API does not require authorization.

## Actions

### Search sounds

> This resource allows searching sounds in Freesound by matching their tags and other kinds of metadata.

*Tags:* `search`

#### Input Parameters
* `query` - _optional_ - The query! The query is the main parameter used to define a query. You can type several terms separated by spaces or phrases wrapped inside quote '"' characters. For every term, you can also use '+' and '-' modifier characters to indicate that a term is "mandatory" or "prohibited" (by default, terms are considered to be "mandatory"). For example, in a query such as query=term_a -term_b, sounds including term_b will not match the search criteria. The query does a weighted search over some sound properties including sound tags, the sound name, its description, pack name and the sound id. Therefore, searching for query=123 will find you sounds with id 1234, sounds that have 1234 in the description, in the tags, etc. You'll find some examples below. Using an empty query (query= or query="") will return all Freeosund sounds.
* `filter` - _optional_ - Allows filtering query results. See below for more information.
* `sort` - _optional_ - Indicates how query results should be sorted. See below for a list of the sorting options. By default `sort=score`. <p> <table>
  <tr>
    <th>Option</th>
    <th>Explanation</th>
  </tr>
  <tr>
    <td>score</td>
    <td>Sort by a relevance score returned by our search engine (default).</td>
  </tr>
  <tr>
    <td>duration_desc
    <td>Sort by the duration of the sounds, longest sounds first.
  </tr>
  <tr>
    <td>duration_asc
    <td>Same as above, but shortest sounds first.
  </tr>
  <tr>
    <td>created_desc
    <td>Sort by the date of when the sound was added. newest sounds first.
  </tr>
  <tr>
    <td>created_asc
    <td>Same as above, but oldest sounds first.
  </tr>
  <tr>
    <td>downloads_desc
    <td>Sort by the number of downloads, most downloaded sounds first.
  </tr>
  <tr>
    <td>downloads_asc
    <td>Same as above, but least downloaded sounds first.
  </tr>
  <tr>
    <td>rating_desc
    <td>Sort by the average rating given to the sounds, highest rated first.
  </tr>
  <tr>
    <td>rating_asc
    <td>Same as above, but lowest rated sounds first.
  </tr>
</table> </p>
    Possible values: score, duration_desc, duration_asc, created_desc, created_asc, downloads_desc, downloads_asc, rating_desc, rating_asc.
* `group_by_pack` - _optional_ - This parameter represents a boolean option to indicate whether to collapse results belonging to sounds of the same pack into single entries in the results list. If `group_by_pack=1` and search results contain more than one sound that belongs to the same pack, only one sound for each distinct pack is returned (sounds with no packs are returned as well). However, the returned sound will feature two extra properties to access these other sounds omitted from the results list: `n_from_same_pack`: indicates how many other results belong to the same pack (and have not been returned) `more_from_same_pack`: uri pointing to the list of omitted sound results of the same pack (also including the result which has already been returned). See examples below. By default `group_by_pack=0`.
* `page` - _optional_ - Query results are paginated, this parameter indicates what page should be returned. By default `page=1`.
* `page_size` - _optional_ - Indicates the number of sounds per page to include in the result. By default `page_size=15`, and the maximum is `page_size=150`. Not that with bigger `page_size`, more data will need to be transferred.

### Details of a sound

> This resource allows the retrieval of detailed information about a sound.

*Tags:* `sound`

#### Input Parameters
* `soundId` - _required_ - ID of the sound that needs to be fetched

## License

**flow**ground :- Telekom iPaaS / freesound-org-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
