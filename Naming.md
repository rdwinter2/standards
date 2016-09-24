# Naming

We have decided in cases where our identifiers can be made public,
that we would assign prefixes to them. The original idea comes from
tracking numbers - e.g if a tracking number starts with '1z' you know
it's UPS and google search can even pull up tracking status
automatically.

We settled on the letter 'F' followed by symbols converted to numbers
using the old pager code alphabet:

    A = 8
    B = 8
    C = 6
    D = 0
    E = 3
    F = 4
    G = 6
    H = 4
    I = 1
    J = 7
    K = 15
    L = 7
    M = 177
    N = 17
    O = 0
    P = 9
    Q = 0
    R = 12
    S = 5
    T = 7
    U = 11
    V = 11
    W = 111
    X = 25
    Y = 4
    Z = 2


By convention, our prefixes are 3 charcters - and unique. Once you
generate a new prefix, pls note here via pull request for discussion.

## Flow Prefixes

    F70 - Prefix for all Flow tracking numbers. Comes from "FLO"

    F96 - Prefix for all unique payment card tokens. Comes from "Flow
    Payment Card" (FPC)

    F17 - Prefix for all one time payment card nonces. Comes from "Flow
    Nonce" (FN)