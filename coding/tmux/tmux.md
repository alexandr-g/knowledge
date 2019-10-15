# tmux

start new:

    tmux

start new with session name:

    tmux new -s myname

attach:

    tmux a  #  (or at, or attach)

attach to named:

    tmux a -t myname

list sessions:

    tmux ls

kill session:

    tmux kill-session -t myname

Kill all the tmux sessions:

    tmux ls | grep : | cut -d. -f1 | awk '{print substr($1, 0, length($1)-1)}' | xargs kill

In tmux, hit the prefix `ctrl+b` (my modified prefix is ctrl+a) and then:

## **Sessions**

    :new<CR>  new session
    s  list sessions
    $  name session

## **Windows (tabs)**

    c  create window
    w  list windows
    n  next window
    p  previous window
    f  find window
    ,  name window
    &  kill window
