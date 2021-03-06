# Download courses from learning sites with `youtube-dl`

You can download whole courses from an array of tutorial sites with the CLI tool `youtube-dl`. In the example further down I'm using my Pluralsight account to get videos from a course at their site. [Here is a list of all supported sites that you can download from with this tool](https://rg3.github.io/youtube-dl/supportedsites.html)

The flags you have to supply may vary depending on which site you make a request to.

**You can get a free 3 month trial to Pluralsight by signing up for free to [Visual Studio Dev Essentials](https://www.visualstudio.com/dev-essentials/)**

## Installation

##### For **macOS/UNIX**

With [`brew`](https://brew.sh/)  for macOS:

```bash
brew install youtube-dl
```

With [`npm`](https://www.npmjs.com/):

```bash
npm install youtube-dl
```

Or you can `curl`/`wget` the thing:

```bash
sudo curl -L https://yt-dl.org/downloads/latest/youtube-dl -o /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl
```
```bash
sudo wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
sudo chmod a+rx /usr/local/bin/youtube-dl
```


##### For Windows

Download with npm as above or just download the `exe`-file from the link below and [put the `exe` in your _PATH_](https://gist.github.com/jesperorb/836cb398e4bb8dc149902d68d3711295).

Or download with `npm` like above.

[Source: youtube-dl download](https://rg3.github.io/youtube-dl/download.html)

## Usage

### Example: download from **Pluralsight**

Run the following command in your terminal to download all the videos to the folder you are currently in. Substitute the example credentials with your own and supply a link to the course.

```bash
youtube-dl --username "youremail@example.com" --password "yourPassword" --verbose --sleep-interval 120 "link to course"
```

Example:

```bash
youtube-dl --username "youremail@example.com" --password "yourPassword" --verbose --sleep-interval 120 "https://app.pluralsight.com/library/courses/javascript-fundamentals/"
```

# IMPORTANT
The argument `--sleep-interval 120` is important. It means that the program will wait 120s (2 minutes) before it downloads the next video. If you don't use this flag _Pluralsight_ will ban you because you are doing too many requests under a short period of time.

>We have blocked your account because our security systems have flagged your Pluralsight account for an unusual amount activity. This does mean a high volume of requests that are in the realm of a request every 10-30 seconds for a prolonged period of time. Please note that this high volume of activity is in violation of our terms of service [https://www.pluralsight.com/terms].