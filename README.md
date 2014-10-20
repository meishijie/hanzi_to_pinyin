hanzi_to_pinyin
==

translate chinese to pinyin, fetch first letter OR full pinyin

## Install

    $ gem 'hanzi_to_pinyin', '0.9.0', require: 'hanzi_to_pinyin'


## Usage

```ruby
  $ HanziToPinyin.hanzi_to_pinyin("中华人民共和国") => "zhrmghg"
  $ HanziToPinyin.hanzi_2_pinyin("中华人民共和国") => "zhrmghg"
  $ HanziToPinyin.hanzi_to_pinyin("喜欢Ruby") => "xhruby"
  $ HanziToPinyin.hanzi_2_pinyin("喜欢Ruby") => "xhruby"

  $ HanziToPinyin.is_hanzi?("你") => true
  $ HanziToPinyin.is_hanzi?("a") => false

  # 多音字,分隔 字字之间;分隔,字母数字保留不变
  $ HanziToPinyin.hanzi_2_py("我们") => "wo;men"
  $ HanziToPinyin.hanzi_2_py("yyf") => "yyf"
  $ HanziToPinyin.hanzi_2_py("查理Smith") => "cha,zha;li;Smith"
  $ HanziToPinyin.hanzi_2_py("测试1") => "ce;shi;1"
  $ HanziToPinyin.hanzi_2_py("测_试") => "ce;_;shi"
  $ HanziToPinyin.hanzi_2_py("测-试") => "ce;-;shi"
  $ HanziToPinyin.hanzi_2_py(2).should == "2"

  $ HanziToPinyin.is_number?("1".ord) => true
  $ HanziToPinyin.is_number?("a".ord) => false

  $ HanziToPinyin.is_underline?("_".ord) => true
  $ HanziToPinyin.is_underline?("豆豆") => false
  $ HanziToPinyin.is_dash?("-".ord) => true
```

## Test
  
    $ rake spec
    
or spec one case
  $ rspec spec/hanzi_to_pinyin/hanzi_to_pinyin_spec.rb -l 21

## Copyright

Copyright (c) 2011 wxianfeng. See LICENSE.txt for
further details.
