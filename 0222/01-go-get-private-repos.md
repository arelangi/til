# go get on private repositories

When I ran `go get github.com/arelangi/SurveyFunky` which is a private repository, I got the following message

```
go get: module github.com/arelangi/SurveyFunky: git ls-remote -q origin in /Users/aditya.relangi/go/pkg/mod/cache/vcs/484ae45f7eb9770f3f35ea0b9f03d397ea6b5e4a67935c53fee1e070a4071579: exit status 128:
	fatal: could not read Username for 'https://github.com': terminal prompts disabled
Confirm the import path was entered correctly.
If this is a private repository, see https://golang.org/doc/faq#git_https for additional information.
```

After visiting the URL, I had to update 

> Git can be configured to authenticate over HTTPS or to use SSH in place of HTTPS. To authenticate over HTTPS, you can add a line to the $HOME/.netrc file that git consults:

> `machine github.com login USERNAME password APIKEY`
> For GitHub accounts, the password can be a personal access token.

Even after making the update, I got a new error when running `go get`

```
go: downloading github.com/arelangi/SurveyFunky v0.0.0-20220201084739-6799ef5e91ea
go get: github.com/arelangi/SurveyFunky@v0.0.0-20220201084739-6799ef5e91ea: verifying module: github.com/arelangi/SurveyFunky@v0.0.0-20220201084739-6799ef5e91ea: reading https://sum.golang.org/lookup/github.com/arelangi/!survey!funky@v0.0.0-20220201084739-6799ef5e91ea: 410 Gone
	server response:
	not found: github.com/arelangi/SurveyFunky@v0.0.0-20220201084739-6799ef5e91ea: invalid version: git fetch -f origin refs/heads/*:refs/heads/* refs/tags/*:refs/tags/* in /tmp/gopath/pkg/mod/cache/vcs/484ae45f7eb9770f3f35ea0b9f03d397ea6b5e4a67935c53fee1e070a4071579: exit status 128:
		fatal: could not read Username for 'https://github.com': terminal prompts disabled
```


What worked finally?




```
go env -w GOPRIVATE=github.com/arelangi
go get github.com/arelangi/SurveyFunky
```