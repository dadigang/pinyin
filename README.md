# 汉语拼音合集包

#### 介绍
汉语拼音合集包

gopher们想必都知道，golang关于都汉语拼音的库少之又少，Shirdon抽空总结了汉语拼音包，包含40000多个字词，基本覆盖了汉语的拼音，
喜欢的朋友欢迎star,fork!共同完善！

#### 用法
`
package main
 import (
 	"fmt"
 	"gitee.com/shirdonl/pinyin/library"
 	"regexp"
 )
 func main() {
 	dict := library.NewDict()
 	s := ""
 	s = dict.Convert(`我，何時成大牛？`, " ").Unicode()
 	fmt.Println(s)
 	// wǒ, hé shí néng bào fù?
 	s = dict.Sentence(`我，何時成大牛？`).Unicode()
 	fmt.Println(s)
 	// ----
 	// 转换接口: Dict.Convert
 	s = dict.Convert(`我爱编程？`, " ").ASCII()
 	fmt.Println(s)
 	// 输入简体中文, 输出为带 连字符- 分隔的拼音字符串
 	// Unicode 格式显示
 	s = dict.Convert(`我，我爱编程？`, "-").Unicode()
 	fmt.Println(s)
 	// 转换简体中文和繁体中文, 转换为带 斜杆/ 分隔的拼音字符串
 	// 不显示声调
 	s = dict.Convert(`我，我爱编程？`, "/").None()
 	fmt.Println(s)
 	// 句子接口: Dict.Sentence
 	// 输入繁体中文, 输出为带 空格 分隔的拼音字符串
 	// ASCII 格式显示
 	s = dict.Sentence(`我，我爱编程？`).ASCII()
 	fmt.Println(s)
 	// 输入简体中文, 输出为带 空格 分隔的拼音字符串
 	// Unicode 格式显示
 	s = dict.Sentence(`我，何时能暴富？`).Unicode()
 	fmt.Println(s)
 	// 转换简体中文和繁体中文, 转换为带 空格 分隔的拼音字符串
 	// 不显示声调
 	s = dict.Sentence(`我，何时能暴富？`).None()
 	fmt.Println(s)
 	// 转换人名: Dict.Name
 	// 输入繁体中文, 输出为带 空格 分隔的人名拼音字符串
 	// ASCII 格式显示
 	s = dict.Name(`万俟沃喜欢吃酸奶`, " ").ASCII()
 	fmt.Println(s)
 	// 输入简体中文, 输出为带 连字符- 分隔的人名拼音字符串
 	// Unicode 格式显示
 	s = dict.Name(`万俟沃喜欢吃酸奶`, "-").Unicode()
 	fmt.Println(s)
 	// 转换简体中文和繁体中文, 转换为带 斜杆/ 分隔的人名拼音字符串
 	// 不显示声调
 	s = dict.Name(`万俟沃喜欢吃酸奶`, "/").None()
 	fmt.Println(s)
 	// 转换拼音简写: Dict.Abbr
 	// 转换简体中文和繁体中文, 输出为带 连字符- 分隔的拼音字符串首字符
 	s = dict.Abbr(`万俟沃喜欢吃酸奶`, "-")
 	fmt.Println(s)
 	// 转换为字符串 slice: ToSlice
 	s = dict.Convert(`我，测试？`, " ").ASCII()
 	fmt.Println(s)
 	fmt.Printf("%v", ToSlice(s))
 
 }
`
