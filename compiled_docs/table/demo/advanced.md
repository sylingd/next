{"title":"扩展","meta":{"title":"扩展","description":"\n<p>通过Table暴露的子组件进行扩展</p>\n","order":"17"},"codes":{"jsx":"import { Table } from '@alifd/next';\nimport PropTypes from 'prop-types';\n/* eslint-disable react/no-multi-comp,react/prop-types */\nconst {Header, Cell} = Table;\nconst dataSource = () => {\n    const result = [];\n    for (let i = 0; i < 5; i++) {\n        result.push({\n            title: `Quotation for 1PCS Nano ${3 + i}.0 controller compatible`,\n            id: 100306660940 + i,\n            time: 2000 + i\n        });\n    }\n    return result;\n};\n\nconst AppHeader = (props, context) => {\n    const {columns} = props;\n    const {onChange} = context;\n    const length = columns[columns.length - 1].length;\n    return (<Header {...props}>\n        <tr>\n            <Cell colSpan={length}>\n                <a onClick={() => onChange(true)} href=\"javascript:;\">Select all</a>&nbsp;\n                <a onClick={() => onChange(false)} href=\"javascript:;\">Unselect all</a>\n            </Cell>\n        </tr>\n    </Header>);\n};\n\nAppHeader.contextTypes = {\n    onChange: PropTypes.func\n};\n\nclass App extends React.Component {\n    static childContextTypes = {\n        onChange: PropTypes.func\n    }\n    state = {\n        selectedKeys: []\n    }\n    getChildContext() {\n        return {\n            onChange: this.onChange\n        };\n    }\n    dataSource = dataSource()\n    onChange = (checked) => {\n        let selectedKeys = [];\n        if (checked) {\n            selectedKeys = this.dataSource.map(item => item.id);\n        }\n        this.onRowChange(selectedKeys);\n    }\n    onRowChange = (selectedKeys) => {\n        this.setState({\n            selectedKeys\n        });\n    }\n    render() {\n        return (<span>\n            <Table dataSource={this.dataSource}\n                components={{\n                    Header: AppHeader\n                }}\n                rowSelection={{\n                    selectedRowKeys: this.state.selectedKeys,\n                    onChange: this.onRowChange\n                }}>\n                <Table.Column title=\"Id\" dataIndex=\"id\" />\n                <Table.Column title=\"Title\" dataIndex=\"title\"/>\n                <Table.Column title=\"Time\" dataIndex=\"time\"/>\n            </Table>\n        </span>);\n    }\n}\n\nReactDOM.render(<App/>, mountNode);\n"},"body":"\n\n````jsx\nimport { Table } from '@alifd/next';\nimport PropTypes from 'prop-types';\n/* eslint-disable react/no-multi-comp,react/prop-types */\nconst {Header, Cell} = Table;\nconst dataSource = () => {\n    const result = [];\n    for (let i = 0; i < 5; i++) {\n        result.push({\n            title: `Quotation for 1PCS Nano ${3 + i}.0 controller compatible`,\n            id: 100306660940 + i,\n            time: 2000 + i\n        });\n    }\n    return result;\n};\n\nconst AppHeader = (props, context) => {\n    const {columns} = props;\n    const {onChange} = context;\n    const length = columns[columns.length - 1].length;\n    return (<Header {...props}>\n        <tr>\n            <Cell colSpan={length}>\n                <a onClick={() => onChange(true)} href=\"javascript:;\">Select all</a>&nbsp;\n                <a onClick={() => onChange(false)} href=\"javascript:;\">Unselect all</a>\n            </Cell>\n        </tr>\n    </Header>);\n};\n\nAppHeader.contextTypes = {\n    onChange: PropTypes.func\n};\n\nclass App extends React.Component {\n    static childContextTypes = {\n        onChange: PropTypes.func\n    }\n    state = {\n        selectedKeys: []\n    }\n    getChildContext() {\n        return {\n            onChange: this.onChange\n        };\n    }\n    dataSource = dataSource()\n    onChange = (checked) => {\n        let selectedKeys = [];\n        if (checked) {\n            selectedKeys = this.dataSource.map(item => item.id);\n        }\n        this.onRowChange(selectedKeys);\n    }\n    onRowChange = (selectedKeys) => {\n        this.setState({\n            selectedKeys\n        });\n    }\n    render() {\n        return (<span>\n            <Table dataSource={this.dataSource}\n                components={{\n                    Header: AppHeader\n                }}\n                rowSelection={{\n                    selectedRowKeys: this.state.selectedKeys,\n                    onChange: this.onRowChange\n                }}>\n                <Table.Column title=\"Id\" dataIndex=\"id\" />\n                <Table.Column title=\"Title\" dataIndex=\"title\"/>\n                <Table.Column title=\"Time\" dataIndex=\"time\"/>\n            </Table>\n        </span>);\n    }\n}\n\nReactDOM.render(<App/>, mountNode);\n````","html":"<script>(function(){'use strict';\n\nvar _createClass = function () { function defineProperties(target, props) { for (var i = 0; i < props.length; i++) { var descriptor = props[i]; descriptor.enumerable = descriptor.enumerable || false; descriptor.configurable = true; if (\"value\" in descriptor) descriptor.writable = true; Object.defineProperty(target, descriptor.key, descriptor); } } return function (Constructor, protoProps, staticProps) { if (protoProps) defineProperties(Constructor.prototype, protoProps); if (staticProps) defineProperties(Constructor, staticProps); return Constructor; }; }();\n\nvar _next = require('@alifd/next');\n\nvar _propTypes = require('prop-types');\n\nvar _propTypes2 = _interopRequireDefault(_propTypes);\n\nfunction _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { default: obj }; }\n\nfunction _classCallCheck(instance, Constructor) { if (!(instance instanceof Constructor)) { throw new TypeError(\"Cannot call a class as a function\"); } }\n\nfunction _possibleConstructorReturn(self, call) { if (!self) { throw new ReferenceError(\"this hasn't been initialised - super() hasn't been called\"); } return call && (typeof call === \"object\" || typeof call === \"function\") ? call : self; }\n\nfunction _inherits(subClass, superClass) { if (typeof superClass !== \"function\" && superClass !== null) { throw new TypeError(\"Super expression must either be null or a function, not \" + typeof superClass); } subClass.prototype = Object.create(superClass && superClass.prototype, { constructor: { value: subClass, enumerable: false, writable: true, configurable: true } }); if (superClass) Object.setPrototypeOf ? Object.setPrototypeOf(subClass, superClass) : subClass.__proto__ = superClass; }\n\n/* eslint-disable react/no-multi-comp,react/prop-types */\nvar Header = _next.Table.Header,\n    Cell = _next.Table.Cell;\n\nvar dataSource = function dataSource() {\n    var result = [];\n    for (var i = 0; i < 5; i++) {\n        result.push({\n            title: 'Quotation for 1PCS Nano ' + (3 + i) + '.0 controller compatible',\n            id: 100306660940 + i,\n            time: 2000 + i\n        });\n    }\n    return result;\n};\n\nvar AppHeader = function AppHeader(props, context) {\n    var columns = props.columns;\n    var onChange = context.onChange;\n\n    var length = columns[columns.length - 1].length;\n    return React.createElement(\n        Header,\n        props,\n        React.createElement(\n            'tr',\n            null,\n            React.createElement(\n                Cell,\n                { colSpan: length },\n                React.createElement(\n                    'a',\n                    { onClick: function onClick() {\n                            return onChange(true);\n                        }, href: 'javascript:;' },\n                    'Select all'\n                ),\n                '\\xA0',\n                React.createElement(\n                    'a',\n                    { onClick: function onClick() {\n                            return onChange(false);\n                        }, href: 'javascript:;' },\n                    'Unselect all'\n                )\n            )\n        )\n    );\n};\n\nAppHeader.contextTypes = {\n    onChange: _propTypes2.default.func\n};\n\nvar App = function (_React$Component) {\n    _inherits(App, _React$Component);\n\n    function App() {\n        var _ref;\n\n        var _temp, _this, _ret;\n\n        _classCallCheck(this, App);\n\n        for (var _len = arguments.length, args = Array(_len), _key = 0; _key < _len; _key++) {\n            args[_key] = arguments[_key];\n        }\n\n        return _ret = (_temp = (_this = _possibleConstructorReturn(this, (_ref = App.__proto__ || Object.getPrototypeOf(App)).call.apply(_ref, [this].concat(args))), _this), _this.state = {\n            selectedKeys: []\n        }, _this.dataSource = dataSource(), _this.onChange = function (checked) {\n            var selectedKeys = [];\n            if (checked) {\n                selectedKeys = _this.dataSource.map(function (item) {\n                    return item.id;\n                });\n            }\n            _this.onRowChange(selectedKeys);\n        }, _this.onRowChange = function (selectedKeys) {\n            _this.setState({\n                selectedKeys: selectedKeys\n            });\n        }, _temp), _possibleConstructorReturn(_this, _ret);\n    }\n\n    _createClass(App, [{\n        key: 'getChildContext',\n        value: function getChildContext() {\n            return {\n                onChange: this.onChange\n            };\n        }\n    }, {\n        key: 'render',\n        value: function render() {\n            return React.createElement(\n                'span',\n                null,\n                React.createElement(\n                    _next.Table,\n                    { dataSource: this.dataSource,\n                        components: {\n                            Header: AppHeader\n                        },\n                        rowSelection: {\n                            selectedRowKeys: this.state.selectedKeys,\n                            onChange: this.onRowChange\n                        } },\n                    React.createElement(_next.Table.Column, { title: 'Id', dataIndex: 'id' }),\n                    React.createElement(_next.Table.Column, { title: 'Title', dataIndex: 'title' }),\n                    React.createElement(_next.Table.Column, { title: 'Time', dataIndex: 'time' })\n                )\n            );\n        }\n    }]);\n\n    return App;\n}(React.Component);\n\nApp.childContextTypes = {\n    onChange: _propTypes2.default.func\n};\n\n\nReactDOM.render(React.createElement(App, null), mountNode);})()</script><div class=\"highlight\"><pre class=\"language-jsx\"><code class=\"language-jsx\"><span class=\"token keyword\">import</span> <span class=\"token punctuation\">{</span> Table <span class=\"token punctuation\">}</span> <span class=\"token keyword\">from</span> <span class=\"token string\">'@alifd/next'</span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">import</span> PropTypes <span class=\"token keyword\">from</span> <span class=\"token string\">'prop-types'</span><span class=\"token punctuation\">;</span>\n<span class=\"token comment\">/* eslint-disable react/no-multi-comp,react/prop-types */</span>\n<span class=\"token keyword\">const</span> <span class=\"token punctuation\">{</span>Header<span class=\"token punctuation\">,</span> Cell<span class=\"token punctuation\">}</span> <span class=\"token operator\">=</span> Table<span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">const</span> <span class=\"token function-variable function\">dataSource</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n    <span class=\"token keyword\">const</span> result <span class=\"token operator\">=</span> <span class=\"token punctuation\">[</span><span class=\"token punctuation\">]</span><span class=\"token punctuation\">;</span>\n    <span class=\"token keyword\">for</span> <span class=\"token punctuation\">(</span><span class=\"token keyword\">let</span> i <span class=\"token operator\">=</span> <span class=\"token number\">0</span><span class=\"token punctuation\">;</span> i <span class=\"token operator\">&lt;</span> <span class=\"token number\">5</span><span class=\"token punctuation\">;</span> i<span class=\"token operator\">++</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        result<span class=\"token punctuation\">.</span><span class=\"token function\">push</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">{</span>\n            title<span class=\"token punctuation\">:</span> <span class=\"token template-string\"><span class=\"token template-punctuation string\">`</span><span class=\"token string\">Quotation for 1PCS Nano </span><span class=\"token interpolation\"><span class=\"token interpolation-punctuation punctuation\">${</span><span class=\"token number\">3</span> <span class=\"token operator\">+</span> i<span class=\"token interpolation-punctuation punctuation\">}</span></span><span class=\"token string\">.0 controller compatible</span><span class=\"token template-punctuation string\">`</span></span><span class=\"token punctuation\">,</span>\n            id<span class=\"token punctuation\">:</span> <span class=\"token number\">100306660940</span> <span class=\"token operator\">+</span> i<span class=\"token punctuation\">,</span>\n            time<span class=\"token punctuation\">:</span> <span class=\"token number\">2000</span> <span class=\"token operator\">+</span> i\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n    <span class=\"token keyword\">return</span> result<span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">const</span> <span class=\"token function-variable function\">AppHeader</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token parameter\">props<span class=\"token punctuation\">,</span> context</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n    <span class=\"token keyword\">const</span> <span class=\"token punctuation\">{</span>columns<span class=\"token punctuation\">}</span> <span class=\"token operator\">=</span> props<span class=\"token punctuation\">;</span>\n    <span class=\"token keyword\">const</span> <span class=\"token punctuation\">{</span>onChange<span class=\"token punctuation\">}</span> <span class=\"token operator\">=</span> context<span class=\"token punctuation\">;</span>\n    <span class=\"token keyword\">const</span> length <span class=\"token operator\">=</span> columns<span class=\"token punctuation\">[</span>columns<span class=\"token punctuation\">.</span>length <span class=\"token operator\">-</span> <span class=\"token number\">1</span><span class=\"token punctuation\">]</span><span class=\"token punctuation\">.</span>length<span class=\"token punctuation\">;</span>\n    <span class=\"token keyword\">return</span> <span class=\"token punctuation\">(</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Header</span></span> <span class=\"token spread\"><span class=\"token punctuation\">{</span><span class=\"token punctuation\">...</span><span class=\"token attr-value\">props</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>tr</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Cell</span></span> <span class=\"token attr-name\">colSpan</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span>length<span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>a</span> <span class=\"token attr-name\">onClick</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token function\">onChange</span><span class=\"token punctuation\">(</span><span class=\"token boolean\">true</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">href</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>javascript:;<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">Select all</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>a</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">&amp;nbsp;\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>a</span> <span class=\"token attr-name\">onClick</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token function\">onChange</span><span class=\"token punctuation\">(</span><span class=\"token boolean\">false</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">href</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>javascript:;<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">Unselect all</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>a</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Cell</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>tr</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n    </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Header</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n\nAppHeader<span class=\"token punctuation\">.</span>contextTypes <span class=\"token operator\">=</span> <span class=\"token punctuation\">{</span>\n    onChange<span class=\"token punctuation\">:</span> PropTypes<span class=\"token punctuation\">.</span>func\n<span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">class</span> <span class=\"token class-name\">App</span> <span class=\"token keyword\">extends</span> <span class=\"token class-name\">React<span class=\"token punctuation\">.</span>Component</span> <span class=\"token punctuation\">{</span>\n    <span class=\"token keyword\">static</span> childContextTypes <span class=\"token operator\">=</span> <span class=\"token punctuation\">{</span>\n        onChange<span class=\"token punctuation\">:</span> PropTypes<span class=\"token punctuation\">.</span>func\n    <span class=\"token punctuation\">}</span>\n    state <span class=\"token operator\">=</span> <span class=\"token punctuation\">{</span>\n        selectedKeys<span class=\"token punctuation\">:</span> <span class=\"token punctuation\">[</span><span class=\"token punctuation\">]</span>\n    <span class=\"token punctuation\">}</span>\n    <span class=\"token function\">getChildContext</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">return</span> <span class=\"token punctuation\">{</span>\n            onChange<span class=\"token punctuation\">:</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>onChange\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n    dataSource <span class=\"token operator\">=</span> <span class=\"token function\">dataSource</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span>\n    <span class=\"token function-variable function\">onChange</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token parameter\">checked</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">let</span> selectedKeys <span class=\"token operator\">=</span> <span class=\"token punctuation\">[</span><span class=\"token punctuation\">]</span><span class=\"token punctuation\">;</span>\n        <span class=\"token keyword\">if</span> <span class=\"token punctuation\">(</span>checked<span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n            selectedKeys <span class=\"token operator\">=</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>dataSource<span class=\"token punctuation\">.</span><span class=\"token function\">map</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">item</span> <span class=\"token operator\">=></span> item<span class=\"token punctuation\">.</span>id<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span>\n        <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span><span class=\"token function\">onRowChange</span><span class=\"token punctuation\">(</span>selectedKeys<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n    <span class=\"token function-variable function\">onRowChange</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token parameter\">selectedKeys</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span><span class=\"token function\">setState</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">{</span>\n            selectedKeys\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n    <span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">return</span> <span class=\"token punctuation\">(</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>span</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table</span></span> <span class=\"token attr-name\">dataSource</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>dataSource<span class=\"token punctuation\">}</span></span>\n                <span class=\"token attr-name\">components</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">{</span>\n                    Header<span class=\"token punctuation\">:</span> AppHeader\n                <span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span>\n                <span class=\"token attr-name\">rowSelection</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">{</span>\n                    selectedRowKeys<span class=\"token punctuation\">:</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>state<span class=\"token punctuation\">.</span>selectedKeys<span class=\"token punctuation\">,</span>\n                    onChange<span class=\"token punctuation\">:</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>onRowChange\n                <span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table.Column</span></span> <span class=\"token attr-name\">title</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>Id<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">dataIndex</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>id<span class=\"token punctuation\">\"</span></span> <span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table.Column</span></span> <span class=\"token attr-name\">title</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>Title<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">dataIndex</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>title<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Table.Column</span></span> <span class=\"token attr-name\">title</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>Time<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">dataIndex</span><span class=\"token attr-value\"><span class=\"token punctuation\">=</span><span class=\"token punctuation\">\"</span>time<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Table</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>span</span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n<span class=\"token punctuation\">}</span>\n\nReactDOM<span class=\"token punctuation\">.</span><span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">App</span></span><span class=\"token punctuation\">/></span></span><span class=\"token punctuation\">,</span> mountNode<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span></code></pre></div>"}