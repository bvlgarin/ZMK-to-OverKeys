
# Default Layer

```plaintext
default_layer {
    display-name = "BASE";
    bindings = <
        &kp Q    &kp W    &kp E    &kp R    &kp T    &kp Y    &kp U    &kp I    &kp O    &kp P
        &kp A    &kp S    &kp D    &kp F    &kp G    &kp H    &kp J    &kp K    &kp L
        &kp Z    &kp X    &kp C    &kp V    &kp B    &kp N    &k M     && kp BSPC
        &k LGUI  && kp LALT && kp SPACE && mo 1 && mo 2 && kp RET
}
```

# Lower Layer

```plaintext
lower_layer {
   display-name = "LOWER";
   bindings = <
       &k N1   && k N2   && k N3   && k N4   && k N5   && k N6   && k N7   && k N8   && k N9   && k N0
       && k EXCL  && k AT  && k HASH  && k DLLR  && k PRCNT  && k CARET  && k AMPS  && k ASTRK  && k LPAR  && K RPAR
       || trans || K MINUS || K EQUAL || K LBKT || K RBKT || K BSLH || K GRAVE
       || trans || trans || trans || trans || mo 1 || trans
   >;
}
```
