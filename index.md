## Repository of NodeJS related links

I will be populating the portal with many-juicy nodejs best practices and frameworks I have gathered.

#### Memory Leaks
You can use the [editor on GitHub](https://github.com/ashutoshkumars/myweb/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

- https://medium.com/tech-tajawal/memory-leaks-in-nodejs-quick-overview-988c23b24dba
- https://marmelab.com/blog/2018/04/03/how-to-track-and-fix-memory-leak-with-nodejs.html
- https://www.toptal.com/nodejs/debugging-memory-leaks-node-js-applications
- https://pm2.io/docs/plus/guide/installation/#install-cpumemory-profiling
- https://nodesource.com/blog/memory-leaks-demystified
- https://github.com/nodejs/help/issues/947
- https://www.valentinog.com/blog/node-usage/
- https://www.nearform.com/blog/how-to-self-detect-a-memory-leak-in-node/
- https://medium.com/yld-blog/cpu-and-i-o-performance-diagnostics-in-node-js-c85ea71738eb
- https://blog.bitsrc.io/memory-leaks-in-nodejs-54ac7bbd4173
- https://marmelab.com/blog/2018/04/03/how-to-track-and-fix-memory-leak-with-nodejs.html
- https://github.com/lloyd/node-memwatch
- https://stackoverflow.com/questions/58875158/nodejs-memory-growth-memory-leak-in-system
- https://stackoverflow.com/questions/59474575/pm2-incorrect-memory-usage-reading-possible-memory-leak-with-node-js-applica
- https://www.phusionpassenger.com/library/walkthroughs/start/nodejs.html
- https://github.com/lovell/sharp/issues/1803
- https://github.com/Unitech/pm2/issues/1453
- https://nodesource.com/blog/memory-leaks-demystified
- https://marmelab.com/blog/2018/04/03/how-to-track-and-fix-memory-leak-with-nodejs.html
- https://medium.com/tech-tajawal/memory-leaks-in-nodejs-quick-overview-988c23b24dba
- https://medium.com/@mohdgadi52/testing-application-without-creating-a-mess-af1a26e9c2c4


What I'd do is start node with node --perf_basic_prof and once it starts spinning, check with perf top -p <pid> what it's doing. At the very least that should tell you if it's actually scavenging.

Forcing a core dump with gcore and inspecting it with lldb+llnode is also a good option.

If live debugging is an option: node --inspect


https://medium.com/tech-tajawal/memory-leaks-in-nodejs-quick-overview-988c23b24dba
https://medium.com/@mohdgadi52/testing-application-without-creating-a-mess-af1a26e9c2c4
https://medium.com/front-end-weekly/my-node-js-memory-leak-and-some-memory-management-and-garbage-collection-6281a5308b4e
https://www.toptal.com/nodejs/debugging-memory-leaks-node-js-applications


If you search for “how to find leak in node” the first tool you’d probably find is memwatch. The original package was abandoned a long time ago and is no longer maintained. However you can easily find newer versions of it in GitHub’s fork list for the repository. This module is useful because it can emit leak events if it sees the heap grow over 5 consecutive garbage collections.


NODE-INSPECTOR
Even a more useful alternative to heapdump, because it allows you to connect to a running application, take heap dump and even debug and recompile it on the fly.


node --trace_gc app.js
https://www.toptal.com/nodejs/debugging-memory-leaks-node-js-applications
https://stackoverflow.com/questions/50709059/maxlistenersexceededwarning-possible-eventemitter-memory-leak-detected-11-mess
https://medium.com/yld-blog/cpu-and-i-o-performance-diagnostics-in-node-js-c85ea71738eb
https://forum.adonisjs.com/t/maxlistenersexceededwarning-possible-eventemitter-memory-leak-detected-11-disconnect-listeners-added/3338/2
https://en.it1352.com/article/7848a710f64b4a70a74e86b8058b6da8.html
https://medium.com/better-programming/make-a-dump-of-the-v8-heap-and-inspect-for-your-node-app-b69f7b68c162
https://medium.com/better-programming/how-to-avoid-memory-leaks-in-node-js-6c08ce1ae67e
https://medium.com/better-programming/make-a-dump-of-the-v8-heap-and-inspect-for-your-node-app-b69f7b68c162
https://medium.com/javascript-in-plain-english/using-parasite-to-debug-nodejs-applications-8c9445358708
![image](https://user-images.githubusercontent.com/3884822/121161293-792ccd80-c86a-11eb-96b6-ac17cf134ba3.png)
