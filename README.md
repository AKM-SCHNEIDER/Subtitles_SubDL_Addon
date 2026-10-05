# SubDL Kodi Add-on

This project is a Kodi subtitles add-on that searches for movie and TV subtitles using the SubDL API and TMDb metadata lookup.

## How it works

- Kodi asks the add-on to search for subtitles for the currently playing item.
- The add-on extracts the media title and uses TMDb to resolve the correct movie or TV episode ID.
- It then sends a subtitle search request to the SubDL API.
- The user picks a subtitle, and the add-on downloads and extracts the subtitle file for Kodi.

## Subtitle language behavior

The add-on no longer hardcodes a single subtitle language in the provider request. It reads the language preferences from Kodi when the subtitle search runs.

In the current implementation, the language is taken from Kodi's subtitle settings and passed to the SubDL API request.

If Kodi does not provide a preferred language, the add-on falls back to English (`en`).

## Required API keys

Update the add-on settings file at `resources/settings.xml` with your own API keys:

```xml
<setting id="TMDBApiKey" type="string">
    <level>4</level>
    <default>YOUR_TMDB_API_KEY</default>
</setting>
<setting id="APIKey" type="string">
    <level>4</level>
    <default>YOUR_SUBDL_API_KEY</default>
</setting>
```

Where to get them:

- SubDL API key: https://subdl.com/panel/api
- TMDb API key: https://www.themoviedb.org/settings/api

## Useful reference

- SubDL language list: https://subdl.com/api-files/language_list.json
- OpenSubtitles reference source: https://github.com/opensubtitlesdev/service.subtitles.opensubtitles-com

## Notes

- The add-on uses Kodi's subtitle language preference when available.
- It is designed for movie and TV subtitle lookup through the SubDL service.

![App Screenshot](https://i.postimg.cc/L4QCZxJr/Screenshot-2024-05-13-at-08-57-23.png)

![App Screenshot](https://i.postimg.cc/vH1P759D/Screenshot-2024-05-13-at-08-58-16.png)


