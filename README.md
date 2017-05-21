This is a qrexec service that allows using pulling from and pushing to another VM on Qubes OS.

Usage
=====

- Add GitRemoteUpload (for `git fetch` or `git pull`) and/or GitRemoteReceive (for `git push`)
  to the server VM. They have to go into /etc/qubes-rpc, so either add them to the template or
  copy them to this directory on startup (see `rc.local`).
- Add git-remote-qvm to `$PATH` in the client VM.
- Optional: Add a policy for GitRemoteUpload and/or GitRemoteReceive. If you don't create it
  yourself, Qubes will offer to create a default policy on first use.
- Use the `qvm` remote with git, e.g. run this in the client VM `git clone qvm://gitvm/home/user/myrepo`
  (`~/myrepo` must exist in the server VM and be a valid git repository)
