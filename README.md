# yarn-berry-workspace

 ## terminal log
```

seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn -v
1.22.19
seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn set version berry
➤ YN0000: Retrieving https://repo.yarnpkg.com/3.3.0/packages/yarnpkg-cli/bin/yarn.js
➤ YN0000: Saving the new release in .yarn/releases/yarn-3.3.0.cjs
➤ YN0000: Done in 0s 348ms
seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn -v
3.3.0
seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn init -w
{
  name: 'yarn-berry-workspace',
  packageManager: 'yarn@3.3.0',
  private: true,
  workspaces: [
    'packages/*'
  ]
}
seob@YUSEOBui-MacBookPro yarn-berry-workspace % 

package.json에서 
"workspaces": [
    "apps/*",
    "packages/*"
  ]
apps 경로설정

seob@YUSEOBui-MacBookPro yarn-berry-workspace % mkdir apps
seob@YUSEOBui-MacBookPro yarn-berry-workspace % cd apps 
seob@YUSEOBui-MacBookPro apps % cd ..
seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn
➤ YN0000: ┌ Resolution step
➤ YN0000: └ Completed
➤ YN0000: ┌ Fetch step
➤ YN0000: └ Completed
➤ YN0000: ┌ Link step
➤ YN0000: └ Completed
➤ YN0000: Done in 0s 33ms


seob@YUSEOBui-MacBookPro yarn-berry-workspace % cd apps
seob@YUSEOBui-MacBookPro apps % yarn create next-app

seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn                   
➤ YN0000: ┌ Resolution step
➤ YN0000: └ Completed
➤ YN0000: ┌ Fetch step
➤ YN0000: └ Completed
➤ YN0000: ┌ Link step
➤ YN0000: │ ESM support for PnP uses the experimental loader API and is therefore experimental
➤ YN0000: └ Completed
➤ YN0000: Done with warnings in 0s 241ms
seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn workspace @wanted/web dev
ready - started server on 0.0.0.0:3000, url: http://localhost:3000
event - compiled client and server successfully in 937 ms (161 modules)
wait  - compiling...
event - compiled successfully in 16 ms (130 modules)
wait  - compiling...
event - compiled successfully in 7 ms (31 modules)



seob@YUSEOBui-MacBookPro yarn-berry-workspace % mkdir packages/lib
seob@YUSEOBui-MacBookPro yarn-berry-workspace % cd packages/lib 
seob@YUSEOBui-MacBookPro lib % mkdir src
seob@YUSEOBui-MacBookPro lib % yarn init
{
  name: 'lib',
  packageManager: 'yarn@3.3.0'
}
seob@YUSEOBui-MacBookPro lib % cd src 
seob@YUSEOBui-MacBookPro src % touch index.ts
seob@YUSEOBui-MacBookPro src % pwd
/Users/seob/IdeaProjects/yarn-berry-workspace/packages/lib/src
seob@YUSEOBui-MacBookPro src % cd ..
seob@YUSEOBui-MacBookPro lib % cd ..
seob@YUSEOBui-MacBookPro packages % cd ..
seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn workspace @wanted/lib add typescript -D
➤ YN0000: ┌ Resolution step
➤ YN0000: └ Completed
➤ YN0000: ┌ Fetch step
➤ YN0000: └ Completed
➤ YN0000: ┌ Link step
➤ YN0000: │ ESM support for PnP uses the experimental loader API and is therefore experimental
➤ YN0000: └ Completed
➤ YN0000: Done with warnings in 0s 353ms
seob@YUSEOBui-MacBookPro yarn-berry-workspace % cd packages/lib 
seob@YUSEOBui-MacBookPro lib % tsc --init
seob@YUSEOBui-MacBookPro lib % cd ..
seob@YUSEOBui-MacBookPro packages % cd ..
seob@YUSEOBui-MacBookPro yarn-berry-workspace % yarn workspace @wanted/web add @wanted/lib



```

💡
yarnrc.yml에
nodeLinker: node-modules
를 추가하면 pnp 모드로 사용하지 않겠다. (yarn1을 사용해도 되고, yarn berry에서 설정해줘도 된다.)
https://yarnpkg.com/getting-started/migration


엔트리 인덱스를 만들어서 사용하는 것을 권장한다!

디자인 시스템에 대해 공부!

📌 Monorepo != Monolith

모노레포 사용시 깃 전략
TBD - Trunk Base Development 


