---
title: "トポロジカル符号のエラー訂正"
permalink: /topological_code_demo/
---

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/two.js/0.7.8/two.min.js"></script>
<script src="/assets/js/topological_code_drawer.js"></script>

## 表面符号

- 頂点: Zスタビライザー　エラーと反可換な時に赤くなる
- 辺：データ量子ビット　Xエラーが起きているときに赤くなる　押すことでXエラーを発生させる
- 面: Xスタビライザー　押すことで現在のエラーにスタビライザーを掛け算する

<div id="surface_code"></div>

## 表面符号のエラー推定

- エラー推定：全ての頂点の赤い輪郭を消す際に、必要な赤い辺の数を最小化する

<div id="surface_code_decode"></div>

## 666 Color code

- 頂点：データ量子ビット　Xエラーが起きているときに黒くなる　押すことでXエラーを発生させる
- 面: Zスタビライザー　Xエラーと反可換な時に明るくなる
- 面: Xスタビライザー　押すことでXエラーを発生させる

<div id="color_code_666"></div>

## 666 Color codeのエラー推定

- エラー推定：全ての明るい面を薄くする際に、必要な黒い頂点数を最小化する

<div id="color_code_666_decode"></div>

## 量子優位性に必要な規模のインスタンス

<div id="surface_code_decode_large"></div>

<div id="color_code_666_decode_large"></div>


<script>
    const distance = 7;
    const surface_code = {
        size: 1000,
        type: "surface_code",
        show_primal: true,
        show_dual: false,
        bind_error: true,
        bind_stabilizer: true,
        distance: distance,
        initial_syndrome: [],
        initial_error: [[],[]],
    };
    const num_flip_SC = 7;
    const num_syndrome_SC = (distance*distance-1)/2;
    const values_SC = Array.from({ length: num_flip_SC }, () => Math.floor(Math.random() * num_syndrome_SC));
    const surface_code_decode = {
        size: 1000,
        type: "surface_code",
        show_primal: true,
        show_dual: false,
        bind_error: true,
        bind_stabilizer: true,
        distance: distance,
        initial_syndrome: values_SC,
        initial_error: [[],[]],
    };
    const color_code_666 = {
        size: 1000,
        type: "color_code_666",
        distance: distance,
        bind_error: true,
        bind_stabilizer: true,
        initial_syndrome: [],
    };

    const num_flip_CC666 = 4;
    const num_syndrome_CC666 = ((3*distance*distance+1)/4-1)/2;
    const values_CC = Array.from({ length: num_flip_CC666 }, () => Math.floor(Math.random() * num_syndrome_CC666));
    const color_code_666_decode = {
        size: 1000,
        type: "color_code_666",
        distance: distance,
        bind_error: true,
        bind_stabilizer: true,
        initial_syndrome: values_CC,
    };

    const large_distance = 23;
    const num_syndrome_SC_large = (large_distance*large_distance-1)/2;
    const num_flip_SC_large = Math.floor(num_syndrome_SC_large*0.1);
    const values_SC_large = Array.from({ length: num_flip_SC_large }, () => Math.floor(Math.random() * num_syndrome_SC_large));
    const surface_code_decode_large = {
        size: 1000,
        type: "surface_code",
        show_primal: true,
        show_dual: false,
        bind_error: true,
        bind_stabilizer: true,
        distance: large_distance,
        initial_syndrome: values_SC_large,
        initial_error: [[],[]],
    };

    const num_syndrome_CC666_large = ((3*large_distance*large_distance+1)/4-1)/2;
    const num_flip_CC666_large = Math.floor(num_syndrome_CC666_large*0.1);
    const values_CC_large = Array.from({ length: num_flip_CC666_large }, () => Math.floor(Math.random() * num_syndrome_CC666_large));
    const color_code_666_decode_large = {
        size: 1000,
        type: "color_code_666",
        distance: large_distance,
        bind_error: true,
        bind_stabilizer: true,
        initial_syndrome: values_CC_large,
    };
    dict = {
        "surface_code": surface_code,
        "surface_code_decode": surface_code_decode,
        "color_code_666": color_code_666,
        "color_code_666_decode": color_code_666_decode,
        "surface_code_decode_large": surface_code_decode_large,
        "color_code_666_decode_large": color_code_666_decode_large,
    }
    for (let name in dict) {
        info = dict[name];
        const element = document.getElementById(name);
        const obj = new TopologicalCodeDrawer(element, info);
        obj.draw();
    }
</script>
